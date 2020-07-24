# Hibernate

## What is Hibernate
Object-relational mapping or ORM is the programming technique to map application domain model objects to the relational database tables. Hibernate is java based ORM tool that provides framework for mapping application domain objects to the relational database tables and vice versa.

We can use Hibernate persistence API for CRUD operations. Hibernate framework provide option to map plain old java objects to traditional database tables with the use of JPA annotations as well as XML based configuration.

## what is JPA

JPA stands for Java Persistence API. It defines a persistence model for object-relational mapping. This is a Java language specification and it lets us map, store, update, and retrieve from relational databases to Java Objects and vice versa

## benefits of using Hibernate Framework?

1. accessing the database by using JDBC. Programmers often write complex SQL queries and map the result to Java objects programmatically. This made application tightly coupled and made it hard to port the application to a different database as SQL syntaxes vary between the databases. we can easily map Java objects to database tables either using XML configuration or annotations.

2. database independency - Hibernate abstracts the SQL queries using higher-level Hibernate Query Language, this allows us to write the same queries independent of the database independently.

3. Hibernate cache helps us in getting better performance:  If you application uses a lot of static data then caching would be a good option and hibernate support caching transparently.

4. Lazy Loading: Lazy Loading means that every time you load an object, hibernate will not load all it's related objects but instead will provide place holders which will be resolved as soon as you try to access them


## Hibernate pros and cons

Pros

* Hibernate uses its own query language HQL and it lets us write queries in a database-independent manner
* Lets us connect Java Classes to Database tables using XML configuration or using annotation
* Hibernate has the ability to cache the results to optimize the read performance
* It supports object inheritance, storing collections to databases

Cons

* Hibernate is slightly less performant compared to JDBC as it has to convert the HQL to its native SQL each time. 
* It runs many SQL queries in the backend based on our object mapping.
* Hibernate is slightly less performant compared to JDBC as it has to convert the HQL to its native SQL each time.  It runs many SQL queries in the backend based on our object mapping.
* Hibernate is slightly less performant compared to JDBC as it has to convert the HQL to its native SQL each time. It runs many SQL queries in the backend based on our object mapping.
* Hibernate doesn’t allow us to insert multiple records into the same table using a single query

* Complex data fetches might lead to multiple iterations of the object-to-table mapping

## Scenario of Hibernate and JDBC

1. Hibernate supports inheritance, associations and collections. These features are not present with JDBC API.

2. Hibernate Query Language (HQL) is more object oriented and close to java programming language. For JDBC, we need to write native sql queries.

3. Hibernate supports caching that is better for performance, JDBC queries are not cached hence performance is low.

4. Hibernate supports JPA annotations, so code is independent of implementation and easily replaceable with other ORM tools. JDBC code is very tightly coupled with the application.

## What is hibernate configuration file?
1. database specific configurations
2. used to initialize SessionFactory.
3. Dialect information, so that hibernate knows the database type and mapping file or class details.

## Annotations
1. `javax.persistence.Entity`: Used with model classes to specify that they are entity beans.
2. `javax.persistence.Table` : Used with entity beans to define the corresponding table name in database.
3. `javax.persistence.Access`: Used to define the access type, either field or property.
4. `javax.persistence.Id`: Used to define the primary key in the entity bean.
5. `javax.persistence.Column`: Used to define the column name in database table.
6. `javax.persistence.GeneratedValue`: Used to define the strategy to be used for generation of primary key. Used in conjunction with javax.persistence.GenerationType enum.
7. `org.hibernate.annotations.Cascade:`: Used to define the cascading between two entity beans, used with mappings.
8. `avax.persistence.PrimaryKeyJoinColumn:`: Used to define the property for foreign key.

## What is Hibernate SessionFactory and how to configure it?
* SessionFactory  is the factory class used to get the Session objects
1. responsible to read the hibernate configuration parameters 
2. connect to the database and provide Session objects

## What is Hibernate Session and how to get it?
* Hibernate Session is the interface between java application layer and hibernate. This is the core interface used to perform database operations. Lifecycle of a session is bound by the beginning and end of a transaction.

* Session provide methods to perform create, read, update and delete operations for a persistent object. We can execute HQL queries, SQL native queries and create criteria using Session object.


## What is difference between openSession and getCurrentSession?
* Hibernate SessionFactory getCurrentSession() method returns the session bound to the context
* Hibernate SessionFactory openSession() method always opens a new session. We should close this session object once we are done with all the database operations.

## What is difference between Hibernate Session get() and load() method?
Hibernate session comes with different methods to load data from database
* get() loads the data as soon as it’s called 
* whereas load() returns a proxy object and loads data only when it’s actually required, so load() is better because it support lazy loading.
* Since load() throws exception when data is not found, we should use it only when we know data exists.
* We should use get() when we want to make sure data exists in the database.

##  How many cache hibernate have
Hibernate caches query data to make our application faster.
1. First Level Cache: Hibernate first level cache is associated with the Session object. Hibernate first level cache is enabled by default and there is no way to disable it. However hibernate provides methods through which we can delete selected objects from the cache or clear the cache completely.

2.Second Level Cache: second-level cache is SessionFactory-scoped, meaning it is shared by all sessions created with the same session factory. is disabled by default but we can enable it through configuration.

3. Query-level is an optional cache for query result sets.

## What are different states of an entity bean?
1. Transient: When an object is never persisted or associated with any session, it’s in transient state. Transient instances may be made persistent by calling save(), persist() or saveOrUpdate(). Persistent instances may be made transient by calling delete().

2. Persistent: When an object is associated with a unique session, it’s in persistent state. Any instance returned by a get() or load() method is persistent.

3. Detached: When an object is previously persistent but not associated with any session, it’s in detached state. Detached instances may be made persistent by calling update(), saveOrUpdate(), lock() or replicate(). The state of a transient or detached instance may also be made persistent as a new persistent instance by calling merge().




## lazy load in hibernate

1. Lazy load: it does not actually load all dependent objects when loading current one . Instead, it loads them when requested to do so
Lazy loading in hibernate improves the performance. It loads the child objects on demand
you have a parent objects and that parent has a collection of children. Hibernate now can "lazy-load" the children, which means that it does not actually load all the children when loading the parent. Instead, it loads them when requested to do so.
"Lazy loading" means that an entity will be loaded only when you actually accesses the entity for the first time.

2. Hibernate intercepts calls to the entity by substituting a proxy for it derived from the entity’s class.
Lazy loading tends to be more useful when large collections are involved.
If you are going to always use something (for sure), you can eager load it.
LAZY loading is used in cases where the related entity size is huge and it's not required to be fetched every time on the other hand


## Hibernate HQL vs SQL
* Hibernate Query Language (HQL). It’s very similar to SQL except that we use Objects instead of table names, that makes it more close to object oriented programming.
* SQL is based on relational database model whereas HQL is a combination of OOPS with Relational database concept.
* SQL manipulates data stored in tables and modifies its rows and columns while HQL is concerned about objects and its properties.
* SQL is concerned about the relationship that exists between two tables while HQL is concerned about relation between objects.
* At the end HQL Queries converted into SQL Queries.
Note: Hibernate runs on top of JDBC driver.


## Hibernate config
```
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
``` 
---

# JPA

## How you will write custom method in the repository in Spring Data JPA? What are rules to define Query methods
1. The name of the query method must start with findBy or getBy  or queryBy or countBy or readBy prefix. The findBy is mostly used by the developer.
2. We can write the query method using multiple fields using predefined keywords(eg. And, Or etc) but these keywords are case sensitive
3. While using findBy or getBy or queryBy or countBy or readBy the character B must be in capital letter,else we will get an exception while deployment.
4. The first character of field name should capital letter.

## What are the important predefined repository interfaces and classes in Spring Data JPA?

* Repository – Top-level interface defined in Spring Data Hierarchy. This is a marker interface i.e doesn’t contain any method.
* CrudRepository – The CrudRepository interface extends Repository interface, provides methods to perform CRUD operatio
* PagingAndSortingRepository – The PagingAndSortingRepository interface extends CrudRepository interface and provides additional methods to retrieve entities using the pagination and sorting.
* JpaRepository – The JpaRepository interface extends PagingAndSortingRepository and QueryByExampleExecutor interface, provides some additional batch methods. See more details here.

## What are the important methods of Crudrepository to perform CRUD operations in Spring Data JPA?

* save(S entity) – Used to save a single entity at a time. 
* saveAll(Iterable<S> – we can save multiple entities at a time.
* findById(ID id) – Use to get entity basis of id
* existsById(ID id) – Used to check whether an entity is already exited in DB for given Id.
* findAll() – Find all entity of particular type.
* findAllById(Iterable<ID> ids)  – Return all entity of given ids.
* count() – Returns the number of entities.
* deleteById(ID id) – Delete the entity on basis of id
* delete(T entity) – delete the entity which one we are passing
* deleteAll() – delete all entities
  
## Difference between CrudRepository and JpaRepository in Spring Data JPA?
*  CrudRepository extends Repository interface.JpaRepository extends PagingAndSortingRepository
*  CrudRepository provides methods to perform CRUD operations.JpaRepository provides additional methods like flush(), saveAndFlush(), deleteInBatch()
*  The saveAll(Iterable entities)  method of CrudRepository returns Iterable.	The saveAll(Iterable entities)  method of JpaRepository returns List.
*  If we have to perform mainly CRUD operation, define our repository using CrudRepository.	If we have to perform CRUD as well as Batch operation define our repository extending JpaRepository.

##  What are the features/benefits of Spring Data JPA?

* Spring Data JPA provides features to Query creation from method names.
* Using Spring Data Jpa we can remove a lot of code by creating an abstract repository class that provides CRUD operations for our entities.
* Spring Data Jpa provides PagingAndSortingRepository interface for sorting and pagination support


## How to enable Spring Data JPA features.

* First, we need to define some configuration class let’s say JpaConfig.java and then we need to use @EnableJpaRepositories annotation with that class.

## Difference between findById() and getOne() in Spring Data JPA?

* The findById() method is available in CrudRepository interface.	 The getOne() method is available in JpaRepositpry interface.
* The findById() method will return null if the record doesn’t exist in the database.	The getOne() method throw EntityNotFoundException if the record doesn’t exist in the database.
* Internally findById() method use EntityManger find() method.	3. Internally getOne() method use EntityManger getReference() method.
* Calling findById() returns a eager fetched entity.	4. Calling getOne() returns a lazily fetched entity.
