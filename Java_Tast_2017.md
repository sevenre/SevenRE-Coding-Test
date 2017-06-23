# Create a spring-boot application
Idea is to create REST api to parse and provide data of public transport domain. TRIAS is an open system which provides data regarding stops/trips of Germany. There are various API to access data. Task of test would be **to fetch** 

  - **nearby stops** for given geo-location which is represented by a pair of latitude and longitude.
  - **trips from given stop** where a given stop is defined by a global stop id.

To improve performance, stops are to be cached in database. Trips are to be fetched in real-time, not stored in database. Expected data-structure for stops & trips is given below.

## Tasks

Here goes the tasks as a list:
* Use TRIAS to fetch stops & trips information (XML req for two endpoints (stop and trip) are below)
* Parse XML and map it to Java class 
![N|Solid](http://i.imgur.com/FEjZw6F.png)
* Given a lat/long bounding box make a 40x40 grid to discretize the bounding box.
* Call TRIAS for all those 1.6k lat/log and get closest stops.
* Store closest stop results in Embedded in-memory database (maintain uniqueness via global-id)
* Create REST-API to fetch stops & trips. The endpoints will be
    * **stop_trias**: from TRIAS (Given lat/long API will provide nearest stop. This should be internally used 1.6k times to fetch the closest stops.)
    * **stop_db**: from Database (Given lat/long and number n API will provide the closest n stops among the 1.6k stops in inmemory database)
    * **trip_trias**: from TRIAS (Given globalId and time get trips from stop)

* Write basic unit-tests for the above REST api

#### Stop API response

```json
[
    {lat, lon, globalId, loc-name, ref-name}
]
```
#### Trip API response

```json
[
    {lat, lon, globalId, loc-name, ref-name}
]
```

## Bonus points
* Use JavaRx & non-blocking code
* Use of java lambda’s
* Swagger documentation of REST api
* Add JWT to secure your REST api

## References
* For parsing XML one can use  [**xpath**](https://docs.oracle.com/javase/tutorial/jaxp/xslt/xpath.html)
* Use following dependencies in `pom.xml`

Embedded database:
 ```xml
<dependency>
   <groupId>com.h2database</groupId>
   <artifactId>h2</artifactId>
</dependency>
```
Enable JPA:
 ```xml
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
``` 
* For embedded database use following lines in `application.yml`
```java
spring:
datasource:
   driver-class-name: org.h2.Driver
   url: jdbc:h2:mem:testdb
   username: sa
   Password:
``` 
* Testing code and implementation
    * https://spring.io/guides/tutorials/bookmarks/
    * https://docs.spring.io/spring-security/site/docs/current/reference/html/test-mockmvc.html
