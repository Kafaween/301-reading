# GraphQL @connection

## Add relationships between types

**@connection**
The @connection directive enables you to specify relationships between @model types. Currently, this supports one-to-one, one-to-many, and many-to-one relationships. You may implement many-to-many relationships using two one-to-many connections and a joining @model type.

**Definition**

```
directive @connection(keyName: String, fields: [String!]) on FIELD_DEFINITION
```

**Usage**
Relationships between types are specified by annotating fields on an @model object type with the @connection directive.

The fields argument can be provided and indicates which fields can be queried by to get connected objects. The keyName argument can optionally be used to specify the name of secondary index (an index that was set up using @key) that should be queried from the other type in the relationship.

When specifying a keyName, the fields argument should be provided to indicate which field(s) will be used to get connected objects. If keyName is not provided, then @connection queries the target table's primary index.

**Has one**
In the simplest case, you can define a one-to-one connection where a project has one team:

```
type Project @model {
  id: ID!
  name: String
  team: Team @connection
}

type Team @model {
  id: ID!
  name: String!
}
```

You can also define the field you would like to use for the connection by populating the first argument to the fields array and matching it to a field on the type:

```
type Project @model {
  id: ID!
  name: String
  teamID: ID!
  team: Team @connection(fields: ["teamID"])
}

type Team @model {
  id: ID!
  name: String!
}
```

Many-to-many connections
You can implement many to many using two 1-M @connections, an @key, and a joining @model. For example:

```
type Post @model {
  id: ID!
  title: String!
  editors: [PostEditor] @connection(keyName: "byPost", fields: ["id"])
}

# Create a join model and disable queries as you don't need them
# and can query through Post.editors and User.posts
type PostEditor
  @model(queries: null)
  @key(name: "byPost", fields: ["postID", "editorID"])
  @key(name: "byEditor", fields: ["editorID", "postID"]) {
  id: ID!
  postID: ID!
  editorID: ID!
  post: Post! @connection(fields: ["postID"])
  editor: User! @connection(fields: ["editorID"])
}

type User @model {
  id: ID!
  username: String!
  posts: [PostEditor] @connection(keyName: "byEditor", fields: ["id"])
}
```
