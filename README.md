## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
`  protocal - a type of network communication w/ standardized rules and format
`  domain - the primary home location of a server
`  path - the file structure of the website
`  port - the location that the server is listening on for certain type of communication(s)
`  query string - addtional instructions that are being sent to the server
`  anchor tag - a location to jump to within a webpage
```

* Name the pieces of the following urls:
	
  * `https://www.google.com/`

```  protocal + domain

  * `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`

``` 	protocal + domain + path

  * `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`

``` 	protocal + domain + port + path + query string + anchor tag

  * `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`

```   protocal + domain + path + anchor tag

* Can a server use more than 1 port?

```   Yes, as it can host many protocals 

* Why is https different than http?
  
```   SSL (indicted by HTTPS) provides for a secure encrypted layer between the client and server.

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```
```   The server is searching for puppies named fido,max, and moxie in animals.


__HTTP Request/Response__

* Name at least 4 http verbs
  
```   GET, POST, PUT, DELETE

* What is each verb useful for in your own words
  
````
`  GET - Used to get/request a webpage, or other Internet based resource
`  POST - Used to send information to a server
`  PUT - Updating infomation that already exists on the server
`  DELETE - Used to delete/remove an object, or other resource, from a server
````
* What does idempotent mean?

````
`  Browser can make the same call repeatedly producing the same result of the server
`  such as PUT and DELETE (more or less). 
````

* Name the 5 http status code ranges.  What are they used for in general?
  
````
`  5XX : General, vague error
`  4XX : Server is working, but couldn't provide what was requested
`  3XX : Redirection to what is being requested
`  2XX : Here's what was requested, but maybe not how you wanted it
`  1XX : Taking a long time to get what was requested, but keep waiting
````

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```   Forward the browser to Google

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
	
```   requests

  * Content-type

```   both

	* User-agent

```   requests

	* Set-cookies

```   responses

	* Cache-control

```   responses

	* Cookie

```   responses

* Is the following a http request or response?  How do you know for each?

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

``` 
`   request, as its a simple query for a resource
```


<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>

```
` response, as a HTML file is being sent to the client
```

DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b

```
` request, as your asking the server to delete a resource
```

__JSON__

* Describe what JSON is.  What is it used for.

```   JavaScript Object Notation -- the most common data exchange format used across the Internet

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}


``` 
` var myObj = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}');
` console.log(myObj.age);
````

* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}

```
`   var myObj = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},{ "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},{ "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},{ "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}');
`
`for (i=0 ; i<myObj.Companies.length ; i++) { console.log(myObj.Companies[i].company); }
````



* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};

```
` var myObj = {company: "Galvanize" , age: 3 , catagories: "Education"};
` var myObjJson = JSON.stringify(myObj);
` console.log(myObjJson);
````


__MISC__

* Describe what DNS is.

``` Domain Name System is a decentralized system of matching URLs with the server IP addresses.

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

``` -x uses the specified proxy, while -v provides "verbose" feedback during the running of commands.

* What is TCP/IP?  How does it interact with HTTP?

``` HTTP rides on top of the TCP/IP layer. TCP/IP (Transmission Control Protocol/Internet Protocol) is the basic communication protocol of the Internet.

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

``` HTTP doesn't break up data into packets. That is done by the TCP/IP layer.