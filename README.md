## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.
```
protocol	
domain
port
path
query string
anchor tag
```

* Name the pieces of the following urls:
	* `https://www.google.com/`
```
 protocol, domain

```

	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
```
 protocol, domain, path

```
	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
```
 protocol, domain, port, path, query string, anchor tag

```
	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
```
 protocol, domain, path, anchor tag  

```

* Can a server use more than 1 port?

```
yes

```
* Why is https different than http?

```
https is secure, it is used for pages that are used to accept information such as passwords. It is a protocol which uses an encrypted HTTP connection by transport-layer security, uses port 443 by default.

http is used to access HTML pages, uses port 80 by default.  

* How does a server interpret the following url's query parameter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie

```
Puppies: “fido”, “max”, “moxie” //clearly moxie is a cat, so I am not certain what the actual display would generate :P

It creates a query string. 

```

__HTTP Request/Response__

* Name at least 4 http verbs

```
Get
Post
Put
Delete 

* What is each verb useful for in your own words

Get — is used to get information/resources of a webpage. When opening a web page you are issuing get. 
Post — used to send information to your server. Like we did in class today for student profiles.  
Put — used to update information on already existing server. 
Delete — used to let the server know you want to delete something.

* What does idempotent mean?

```
idempotent operation is a type that has no effect if it is performed more then one time as long as it has the same input parameters. 


* Name the 5 http status code ranges.  What are they used for in general?

```
Informational
Successful 
Redirection 
Client Error
Server Error 

They allow communication between servers and client. https://http.cat/

```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
This status code lets the client know that the page/resources they are requesting have been moved, it provides the new redirected address, and lets the client know that in the future they should use the new provided URL. 


* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
```
request
```
	* Content-type
```
response

````
	* User-agent
```
request
```
	* Set-cookies
```
request 
```

	* Cache-control
```
both

```
	* Cookie
```
both
```

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
response 

because the client is receiving information from the sight. 
```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```
request

The client is requesting to delete 

__JSON__

* Describe what JSON is.  What is it used for.
JavaScript Object Notation, it is data exchange format for the web, the data it consist of is only a string that represents objects like arrays + objects. It is used for parsing with Javascript. 

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}

```
var jsonObj JSON.parse (‘ { "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"} ‘);

consloe.log(jsonObj,age);
 

```


* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```
var comp = JSON.parse ('{ "Companies":[ { "company": "Github", "age": 7, "categories":"Services,Internet,Software"},{ "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},{ "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},{ "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}')
comp.Companies.forEach(function(val){
console.log(val.company);

}); 

```

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```
console.log('myObj: ' + JSON.stringify(myObj));

```
__MISC__

* Describe what DNS is.
```
 It's a way of relating human understandable names like site address to the numeric addresses computers use lacked IP addresses.  So it maps human address to numeric computer address.  
```

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
Curl -vIs verbose mode it will print out more information about what's going oncurl -XIs to specify a certain request method when talking to the server.  The default is GET but you can specify something else with this flag.
```

* What is TCP/IP?  How does it interact with HTTP?
```
HTTP is broken down into smaller packets via TCP/IP for more efficient transport and error handling through all the servers and switches to get between the client and server.

````

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?
```
No, I think that it is happening at the transport layer via TCP or Transmission Control Protocol.HTTP is a way for clients and server to request and transmit chunks of what a user wants.  These are broken down into smaller packets via TCP/IP for more efficient transport and error handling through all the servers and switches to get between the client and server.
