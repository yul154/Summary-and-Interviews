Hibernate
* How many cache hibernate have

First Level Cache: Hibernate first level cache is associated with the Session object. Hibernate first level cache is enabled by default and there is no way to disable it. However hibernate provides methods through which we can delete selected objects from the cache or clear the cache completely.
Second Level Cache: second-level cache is SessionFactory-scoped, meaning it is shared by all sessions created with the same session factory. is disabled by default but we can enable it through configuration.
Query-level is an optional cache for query result sets.


* lazy load in hibernate

Lazy load: it does not actually load all dependent objects when loading current one . Instead, it loads them when requested to do so
Lazy loading in hibernate improves the performance. It loads the child objects on demand
you have a parent objects and that parent has a collection of children. Hibernate now can "lazy-load" the children, which means that it does not actually load all the children when loading the parent. Instead, it loads them when requested to do so.
"Lazy loading" means that an entity will be loaded only when you actually accesses the entity for the first time.

@OneToMany(fetch = FetchType.LAZY, mappedBy = "user")
Hibernate intercepts calls to the entity by substituting a proxy for it derived from the entity’s class.
Lazy loading tends to be more useful when large collections are involved.
If you are going to always use something (for sure), you can eager load it.
LAZY loading is used in cases where the related entity size is huge and it's not required to be fetched every time on the other hand


* Hibernate HQL vs SQL
SQL is based on relational database model whereas HQL is a combination of OOPS with Relational database concept.
SQL manipulates data stored in tables and modifies its rows and columns while HQL is concerned about objects and its properties.
SQL is concerned about the relationship that exists between two tables while HQL is concerned about relation between objects.
At the end HQL Queries converted into SQL Queries.
Note: Hibernate runs on top of JDBC driver.

* Hibernate config
hibernate.connection.driver_class
JDBC driver class
hibernate.connection.url
JDBC URL
hibernate.connection.username
database user
hibernate.connection.password
database user password
Hibernate.connection.pool_size
hibernate.connection.autocommit
maximum number of pooled connections
Allows autocommit mode to be used for the JDBC connection.
 

