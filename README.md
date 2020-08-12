Для указания таймаута для монги можно поступить так:

Вместо этих настроек:
```properties
spring.data.mongodb.host=myHost
spring.data.mongodb.port=27017
spring.data.mongodb.database=myDatabase
spring.data.mongodb.username=myUser
spring.data.mongodb.password=myPassword
```

Указать эти:
```properties
spring.data.mongodb.uri=mongodb://myUser:myPassword@myHost:27017,myHost:27017/myDatabase?serverSelectionTimeoutMS=2000&connectTimeoutMS=2000
spring.data.mongodb.database=myDatabase
spring.data.mongo.repositories.enabled=true
```
Например,

```yaml
application:
  mongodb:
    host: localhost
    port: 27017
    database: myDatabase

spring:
  data:
    mongodb:
      uri: mongodb://${application.mongodb.host}:${application.mongodb.port}/${application.mongodb.database}?serverSelectionTimeoutMS=2222
```
