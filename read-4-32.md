# Serverless and Amplify

## What is Serverless

**Serverless** is a cloud computing execution model where the cloud provider dynamically manages the allocation and provisioning of servers. A serverless application runs in stateless compute containers that are event-triggered, ephemeral (may last for one invocation), and fully managed by the cloud provider. Pricing is based on the number of executions rather than pre-purchased compute capacity

**Serverless applications** are event-driven cloud-based systems where application development rely solely on a combination of third-party services, client-side logic and cloud-hosted remote procedure calls (Functions as a Service).

**currently available cloud services:**

    1. AWS Lambda
    2. Google Cloud Functions
    3. Azure Functions
    4. IBM OpenWhisk
    5. Alibaba Function Compute
    6. Iron Functions
    7. Auth0 Webtask
    8. Oracle Fn Project
    9. Kubeless


#
## API (GraphQL)

The GraphQL Transform provides a simple to use abstraction that helps you quickly create backends for your web and mobile applications on AWS. With the GraphQL Transform, you define your application's data model using the GraphQL Schema Definition Language (SDL) and the library handles converting your SDL definition into a set of fully descriptive AWS CloudFormation templates that implement your data model.

For example you might create the backend for a blog like this:

```
type Blog @model {
  id: ID!
  name: String!
  posts: [Post] @connection(name: "BlogPosts")
}
type Post @model {
  id: ID!
  title: String!
  blog: Blog @connection(name: "BlogPosts")
  comments: [Comment] @connection(name: "PostComments")
}
type Comment @model {
  id: ID!
  content: String
  post: Post @connection(name: "PostComments")
}
```

The GraphQL Transform simplifies the process of developing, deploying, and maintaining GraphQL APIs. With it, you define your API using the GraphQL Schema Definition Language (SDL) and can then use automation to transform it into a fully descriptive cloudformation template that implements the spec. The transform also provides a framework through which you can define your own transformers as @directives for custom workflows.

**API Category Project Structure**

At a high level, the transform libraries take a schema defined in the GraphQL Schema Definition Language (SDL) and converts it into a set of AWS CloudFormation templates and other assets that are deployed as part of amplify push. The full set of assets uploaded can be found at amplify/backend/api/YOUR-API-NAME/build.

When creating APIs, you will make changes to the other files and directories in the amplify/backend/api/YOUR-API-NAME/ directory but you should not manually change anything in the build directory. The build directory will be overwritten the next time you run amplify push or amplify api gql-compile. Here is an overview of the API directory:

```
-build/
- resolvers/
| # Store any resolver templates written in vtl here. E.G.
|-- Query.ping.req.vtl
|-- Query.ping.res.vtl
|
- stacks/
| # Create custom resources with CloudFormation stacks that will be deployed as part of `amplify push`.
|-- CustomResources.json
|
- parameters.json
| # Tweak certain behaviors with custom CloudFormation parameters.
|
- schema.graphql
| # Write your GraphQL schema in SDL
- schema/
| # Optionally break up your schema into many files. You must remove schema.graphql to use this.
|-- Query.graphql
|-- Post.graphql
- transform.conf.json

```
