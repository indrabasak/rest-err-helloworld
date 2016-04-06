*****************************************
Testing TypeMismatchException exception
*****************************************
URL: http://localhost:8080/rest-err-helloworld/customers/abc
HTTP Method: GET
Header: Accept: application/xml

Expected Result
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<errorInfo>
    <url>http://localhost:8080/rest-err-helloworld/customers/abc</url>
    <code>400</code>
    <type>typeMismatch</type>
    <message>Customer cannot have id: abc</message>
</errorInfo>

*****************************************
Testing CustomerNotFoundException exception
*****************************************
URL: http://localhost:8080/rest-err-helloworld/customers/10
HTTP Method: GET
Header: Accept: application/xml

Expected Result
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<errorInfo>
    <url>http://localhost:8080/rest-err-helloworld/customers/10</url>
    <code>400</code>
    <type>customerNotFound</type>
    <message>Customer not found - Customer with id 10 not found.</message>
</errorInfo>



