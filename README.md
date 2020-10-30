
# Saina Farm  API Documentation by Dominic Imbuga updated Jan 2019.

## Our Mission

Saina Farm platform exposes critical operational data insights to more than 1 in 3 Africa row crop farmers.

## In Markdown

Inspired by [@iros](https://github.com/iros)'s [documentation
gist](https://gist.github.com/iros/3426278).

Our focus is on creating a comprehensive, structured and
helpful API documentation. Structure should be regular and repeated across
endpoints and between projects.


Our mission is to help bring farmers the future of farming. We challenge what is possible and invent new ways of applying cutting-edge technology to the world's oldest and most foundational industry.

Farmers are the core of agriculture and we help them use technology to be more successful. Farmer success is our success. We will never make a decision that doesn't benefit farmers.

Our  world depends on agriculture. By making farming more efficient and helping farmers grow more using less, We have the opportunity to make a massive positive impact.

And, We've brought together a world-class team to make it happen.

## By example

All information about your API call are provided by example:

* [Examples](examples) - For each API call, a completed anonymised example.
Where possible this example comes from a real API.

## Ringa RestFul API

Do what you want more, [SainaFarm](https://sainafarm.herokuapp.com/), spread the word.

**Title**
----
  <_Additional information about your API call. 

  I shoud Later Consider :
  How would you describe the Header part;  
  to differentiate from Data Param? For instance,
   the Content-Type and Authorization.
   Not  long Dom, imagine you have 10 endpoints with wildcards in them, would blow out of the proportion and make this unreadable.
   really fit the case when there are several operations available for the same URL (like POST/GET/PUT ...)
In this case, all of them could have the same header as well as URL but different reminder :)
Would you put query parameters in the URL parameters area?
add header to request. then how can I do ?
ie. x-access-token: ''
It's much more attractive to render this as an actual table, which actually matches the format you used in your blog 
Note: Usage of : in section headers in the template is inconsistent
Example, URL doesn't have :, Method: does have :. Might be worthwhile to standardize.

  
  Try to use verbs that match both request type (fetching vs modifying) and plurality (one vs multiple)._>

* **URL**

  <_The URL Structure (path only, no root url)_>

* **Method:**
  
  <_The request type_>

  `GET` | `POST` | `DELETE` | `PUT`
  
*  **URL Params**

   <_If URL params exist, specify them in accordance with name mentioned in URL section. Separate into optional and required. Document data constraints._> 

   **Required:**
 
   `id=[integer]`

   **Optional:**
 
   `photo_id=[alphanumeric]`

* **Data Params**

  <_If making a post request, what should the body payload look like? URL Params rules apply here too._>

* **Success Response:**
  
  <_What should the status code be on success and is there any returned data? This is useful when people need to to know what their callbacks should expect!_>

  * **Code:** 200 <br />
    **Content:** `{ id : 12 }`
 
* **Error Response:**

  <_Most endpoints will have many ways they can fail. From unauthorized access, to wrongful parameters etc. All of those should be liste d here. It might seem repetitive, but it helps prevent assumptions from being made where they should be._>

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "Log in" }`

  OR

  * **Code:** 422 UNPROCESSABLE ENTRY <br />
    **Content:** `{ error : "Email Invalid" }`

* **Sample Call:**

  <_Just a sample call to your endpoint in a runnable format ($.ajax call or a curl request) - this makes life easier and more predictable._> 

* **Notes:**

  <_This is where all uncertainties, commentary, discussion etc. can go. I recommend timestamping and identifying oneself when leaving comments here._> 


  **Show User**
----
  Returns json data about a single user.

* **URL**

  /users/:id

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
 
   `id=[integer]`

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ id : 12, name : "Michael Bloom" }`
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "User doesn't exist" }`

  OR

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/users/1",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
