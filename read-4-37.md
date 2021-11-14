# Amazon S3

+ Amazon Simple Storage Service (Amazon S3) is storage for the Internet. It is designed to make web-scale computing easier. 
+ Amazon S3 has a simple web services interface that you can use to store and retrieve any amount of data, at any time, from anywhere on the web.
+ A bucket is a container for objects stored in Amazon S3. Every object is contained in a bucket.
+ Objects are the fundamental entities stored in Amazon S3. Objects consist of object data and metadata. The data portion is opaque to Amazon S3. The metadata is a set of name-value pairs that describe the object.
+ A key is the unique identifier for an object within a bucket. Every object in a bucket has exactly one key.
+ You can choose the geographical AWS Region where Amazon S3 will store the buckets that you create. 
+ Amazon S3 provides strong read-after-write consistency for PUTs and DELETEs of objects in your Amazon S3 bucket in all AWS Regions.


### Advantages of using Amazon S3

+ Creating buckets: Create and name a bucket that stores data.

+ Storing data: Store an infinite amount of data in a bucket.

+ Downloading data: Download your data or enable others to do so.

+ Permissions: Grant or deny access to others who want to upload or download data into your Amazon S3 bucket.
+ Standard interfaces: Use standards-based REST and SOAP interfaces designed to work with any internet-development toolkit.


### S3 features

1. Storage classes: offers a range of storage classes designed for different use cases.
2. Bucket policies: provide centralized access control to buckets and objects based on a variety of conditions.
3. AWS Identity and Access Management: You can use AWS Identity and Access Management (IAM) to manage access to your Amazon S3 resources.
4. Access control lists: control access to each of your buckets and objects using an access control list (ACL).
5. Versioning: use versioning to keep multiple versions of an object in the same bucket.
6. Operations: there are alot of operations like :

+ Create a bucket – Create and name your own bucket in which to store your objects.
+ Write an object – Store data by creating or overwriting an object. When you write an object, you specify a unique key in the namespace of your bucket. This is also a good time to specify any access control you want on the object.
+ Read an object – Read data back. You can download the data via HTTP.
+ Delete an object – Delete some of your data.
+ List keys – List the keys contained in one of your buckets. You can filter the key list based on a prefix.


