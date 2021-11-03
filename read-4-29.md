# Room

## Save data in a local database using Room 

- The most common use case is to cache relevant pieces of data so that when the device cannot access the network, the user can still browse that content while they are offline.


**The Room** persistence library provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite. In particular, Room provides the following benefits:

1. Compile-time verification of SQL queries.
2. Convenience annotations that minimize repetitive and error-prone boilerplate code.
3. Streamlined database migration paths.


## Primary components
There are three major components in Room:

1. Database Class 
2. Data Entities
3. Data Access Object

The image bellow illistrate the relation between room components:

![img](https://developer.android.com/images/training/data-storage/room_architecture.png)
