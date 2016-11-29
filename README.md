[![Build Status][travis-badge]][travis-badge-url]

Rest Error Hello World
===================
This is  a simple example for error handling in a REST service. This is the continuation of the previous 
[REST Hello World Example](https://github.com/indrabasak/rest-helloworld).

# Build
Execute the following command from the parent directory to compile the project:

```
mvn clean install
```
Once the build completes successfully, you should have the artifact `rest-err-helloworld.war` in the `target` folder.

# Deploy
You can deploy the `rest-err-helloworld.war` in a [Tomcat](http://tomcat.apache.org/) web container or any other JEE web 
container of your choice.

# Test
You can test it using RESTClient or Postman. This project has been tested using RESTClient. 
To test follow the steps below:

1. Download WizTools.org RESTClient.
2. Start REST Client: java -jar restclient-ui-3.4-jar-with-dependencies.jar

#### Testing TypeMismatchException Exception
URL:` http://localhost:8080/rest-err-helloworld/customers/abc`
HTTP Method: GET
Header: Accept: application/xml

Expected Result
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<errorInfo>
    <url>http://localhost:8080/rest-err-helloworld/customers/abc</url>
    <code>400</code>
    <type>typeMismatch</type>
    <message>Customer cannot have id: abc</message>
</errorInfo>
```

#### Testing CustomerNotFoundException Exception
URL: `http://localhost:8080/rest-err-helloworld/customers/10`
HTTP Method: GET
Header: Accept: application/xml

Expected Result
```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<errorInfo>
    <url>http://localhost:8080/rest-err-helloworld/customers/10</url>
    <code>400</code>
    <type>customerNotFound</type>
    <message>Customer not found - Customer with id 10 not found.</message>
</errorInfo>
```

If you are interested in knowing more about this project, you can find in my blog 
['REST API and Error Handling'](https://indrabasak.wordpress.com/2016/04/06/rest-api-and-error-handling/).


[travis-badge]: https://travis-ci.org/indrabasak/rest-err-helloworld.svg?branch=master
[travis-badge-url]: https://travis-ci.org/indrabasak/rest-err-helloworld/

