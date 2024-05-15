<h1>API Testing Project for Restful API</h1>

The scope of this project is to use all  API knowledge gained throught the Software Testing course and apply them in practice, using a live application.

Application under test: Restful API

Tools used: Postman, Newman

Collection link: https://api.restful-api.dev/

<h2>Tests performed</h2>

<ol>
<li>List of objects by ID's</li>

HTTP method for request: GET https://api.restful-api.dev/objects?id=2&id=6&id=11 <br>
Request description: This GET request lists all of the objects stored from the API's database with the requested ID, in my example id number 2 6 and 11 <br>
Test types / techniques used: Number of objectsis equal with 3 and Every name contains "apple" word <br>
Response status code: 200OK <br>

Below you can find a picture of the API request from Postman:<br>

![image](https://github.com/BalintRPD/Project-final-rp-d/assets/165387441/ec6ff104-5392-48ff-a423-af05e8fdc3a4)



JavaScript Tests:

![image](https://github.com/BalintRPD/Project-final-rp-d/assets/165387441/a48b5b5c-a894-4c95-8b00-5be631b9af71)



<li>POST: Add an object</li>

HTTP method for request: POST: https://api.restful-api.dev/objects <br>
Request description: This POST request adds a new obiect with totally new lines,datas resulting an unique ID number<br>
Test types / techniques used: Status code is 200 and Response time is less then 4s <br>
Response status code: 200OK <br>

Below you can find a picture of the API request from Postman:<br>

![image](https://github.com/BalintRPD/Project-final-rp-d/assets/165387441/3b09d553-ca85-4b77-a59a-913cc59441be)
<br>

JavaScript Tests:
![image](https://github.com/BalintRPD/Project-final-rp-d/assets/165387441/de893226-adef-4c15-b0bd-1ca097dc0720)

<br>


<li>PUT Update object</li>

HTTP method for request: PUT https://api.restful-api.dev/objects<br>
Request description: This PUT request adds new line/s to a specific ID s object<br>
Test types / techniques used: White box testing<br>
Response status code: Not to contain "doesn 't exist" and Status code is 200 <br>

Below you can find a picture of the API request from Postman:<br>

![image](https://github.com/BalintRPD/Project-final-rp-d/assets/165387441/b7b69ff5-1f08-4350-be54-16bb929326d1)
<br>

JavaScript Tests:

![image](https://github.com/BalintRPD/Project-final-rp-d/assets/165387441/8003c71f-6346-42d1-945a-60076d7ce08b)

<br>

</ol>

<h2>Execution report for the created API collection </h2>

Below you can find the execution report that was generated through the Postman collection runner. <br>

![image](https://github.com/BalintRPD/Project-final-rp-d/assets/165387441/b5592b6d-10cd-4679-b3db-a29c334d0b93)
![image](https://github.com/BalintRPD/Project-final-rp-d/assets/165387441/90e0c9b0-3f04-4aff-b974-75f872648823)

<br>

The collection was also run through newman directly from the terminal, and the results can be found below:<br>

![image](https://github.com/BalintRPD/Project-final-rp-d/assets/165387441/687266a4-4d41-49dd-8329-47c17d3f5cc1)

<br>

<h2>Defects found</h2>

The following issues were identified while running the postman tests:<br>

Bug No 1.
With the GET Get all objects request the user can't get the personally added objects listed, the user can add as many obiects to the API s database the GET Get all request wont show it

Bug No 2.
With the PATCH Update an object request the user normally can update one or more lines from an object but this PATCH request can update normally only the "name" line, if the user updates/patches a value from the "data" section then all of the unupdated lines will be deleted, for example I like to update the color line and all of the other lines will be deleted, the color line will be updated only.

<h2>Conclusions</h2>

This Restful API is almost ready to publish as 100% passed, the only things I have experienced are the following:
-After the execution of 11 tests 10 has passed and only 1 is failed meaning that the 90.90% of the tests are passed
-The GET Get all objects request do not bring up the manually added objects by the user with the POST Add an object request
-The PATCH Update object request can update/patch correctly only the "name" value, the other values from the "data" field will be deleted, only the patched line will stay they (for example I PATCH the "color" value to "Yellow" for oject with ID=1 and the "capacity value will dissapear, only the "color" : "Yellow" will stay there
-There are some performance issues, while executing the same request for example the GET Get all objects will have the response time of 300ms 900ms and even 3 or 4 seconds to, so the performance is not stable on the servers side. These tests were made without any extra network using apps on my PC.
My opinion is that the Restful API is a user friendly API with a few bugs to fix, the majority of the functionalities are working perfectly with some performance issues on the API's server side.


