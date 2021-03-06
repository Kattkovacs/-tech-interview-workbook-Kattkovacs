# Web with Python questions

## Software design

### Clean code

#### 1. Point out 5 suggestions, how to format an SQL query!

1. Explain your queries in comments.
2. Keep the queries readable with proper indentation and alignment.
3. Avoid repetition.
4. A reusable query should do one thing, and do it properly.
5. Name objects in your database logically and consistently.

#### 2. What layers can you name in a simple web application?

Presentation (UI), Application, Data

### Error handling

#### 3. What error can occur, when an array does not have an element on the requested index?

IndexError: List index out of range

#### 4. What is the “finally” block, and how would you use it?

The try statement can have a finally block (it is optional). It executes no matter what, as the last step of the error handling.

#### 5. Why should we catch special exception types?

General exceptions will not let you know the exact root cause of the issue especially if many steps are involved in a method implementation. Also, in many cases, we need to react to errors based on their type with different exception handling.

### Security

#### 6. What is SQL injection? How to protect an application against it?

SQL injection is a technique by which vulnerable (poorly designed) web applications can be attacked by harming the database. You can protect your application by: sanitizing user input, escaping, parameterising (%s), random table names

#### 7. What is XSS? How to protect an application against it?

XSS (also called cross-site scripting) is a web security vulnerability that allows an attacker to compromise the interactions that users have with a vulnerable application. It is often used to impersonate a user and access data/funcionalities/permissions that the user has. It is based on manipulating a vulnerable web site so that it returns malicious JavaScript to users. You can protect your application by: filter input, encode data on output, use Content Security Policy.

#### 8. How to properly store passwords?

Hashed and salted.

#### 9. What is HTTPS?

Hypertext Transfer Protocol Secure. It is used for secure communication in a network and widely used on the internet. It protects the privacy and integrity of the exchanged data and prevents third-party attacks. HTTPS uses an encryption protocol to encrypt communications. The protocol is called Transport Layer Security (TLS). This protocol secures communications by using what’s known as an asymmetric public key infrastructure.

#### 10. What is encryption and decryption?

Encryption is the practice of modifying information in a way that only someone with a corresponding key can get the original data and read it. It is a two-way function, which means that encripted data can be decrypted with the appropriate key.

#### 11. What is hashing?

Hashing is the practice of using an algorithm to map data. Unlike encryption, it is a one-way function. It is often used to store passwords.

#### 12. What is the difference between encryption and hashing? When would you use which?

Encryption is a two-way function, while hashing is one-way. Encryption is meant protect data in transit and hashing is meant to verify if the examined data have been modified or not.

#### 13. What encryption methods do you know?

Triple DES, RSA, Blowfish, Twofish, AES

#### 14. What hashing methods do you know?

Division-remainder method, folding method, radix transformation method, digit rearrangement method

#### 15. How/where would you store sensitive data (like db password, API key, ...) of your application?

In environment variables

## Computer science

### Algorithms

#### 16. What is the difference between Stack and Queue data structure?

**Stack:** A stack is a linear data structure in which elements can be inserted and deleted only from one side of the list, called the top. A stack follows the LIFO (Last In First Out) principle, i.e., the element inserted at the last is the first element to come out. The insertion of an element into stack is called push operation, and deletion of an element from the stack is called pop operation. In stack we always keep track of the last element present in the list with a pointer called top.
**Queue:** A queue is a linear data structure in which elements can be inserted only from one side of the list called rear, and the elements can be deleted only from the other side called the front. The queue data structure follows the FIFO (First In First Out) principle, i.e. the element inserted at first in the list, is the first element to be removed from the list. The insertion of an element in a queue is called an enqueue operation and the deletion of an element is called a dequeue operation. In queue we always maintain two pointers, one pointing to the element which was inserted at the first and still present in the list with the front pointer and the second pointer pointing to the element inserted at the last with the rear pointer.

#### 17. What is BubbleSort? Describe the main logic of this sorting algorithm.

Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in wrong order.

```python
def bubbleSort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1] :
                arr[j], arr[j+1] = arr[j+1], arr[j]
```

#### 18. Explain the process of finding the maximum and minimum value in a list of numbers!

Assign a variable to min and max which are both the first elements of the array.
Then loop through the array starting from the second element and examine each element.
If the examined element is bigger than the value assigned to the max variable,
change the max variable value to that element. Same with the min, but the condition is that
the examined element is smaller.

#### 19. Explain the process of calculating the average value in an array of numbers!

Sums up the values of the array and divides the sum with the length of the array.

#### 20. What is Big O complexity? Explain time and space complexity!

Big O Notation is the language we use to describe the complexity of an algorithm,
we use it for talking about how long an algorithm takes to run.
It is how we compare the efficiency of different approaches to a problem.
With Big O Notation we express the runtime in terms of — how quickly it grows relative to the input,
as the input gets larger.
Time: O(1) & O(log n) < O(n) < O (n log n) < O(n^2) < O(2^n) < O(n!)
Space: memory optimization

#### 21. Explain the process of calculating the average value in a linked list of numbers!

Summing the values and dividing them by the list length.

### Procedural

#### 22. How the CASE condition works in SQL?

The CASE statement goes through conditions and returns a value when the first condition is met.
Once a condition is true, it will return the result and won't read the further conditions in the CASE statement.
In case there are no true conditions, the ELSE clause will apply.

#### 23. How the switch-case condition works in JavaScript?

The switch statement is used to perform different actions based on different conditions

#### 24. How to achieve a switch-case-like structure in Python?

Define a function with one parameter.
Inside a the function create a dictionary with keys being the 'case' values
and values being the return values of that case statement.
The function should return the dictionary.get(parameter, default case).

#### 25. Explain variable scoping in Python!

Where a variable is accessible depends on how it is defined.
We call the part of a program where a variable is accessible its scope.

#### 26. What’s the difference between const and var in JavaScript?

Const is block scoped and cannot be reassigned, var is function scoped and can be reassigned

#### 27. How the list comprehension looks like in Python?

```python
_result_ = [*transform* *iteration* *filter*]
num_list = [ i for i in range(10) ]
```

#### 28. How the “ternary expression” looks like in Python?

if 'condition' is True:
'condition_is_true'
else:
'condition_is_false'

#### 29. How the ternary expression looks like in JavaScript?

```javascript
if ("condition" === true) {
  ("condition_is_true");
} else {
  ("condition_is_false");
}
```

#### 30. How to import a function from another module in Python?

from [module-name] import [function-name]

#### 31. How to import a function from another module in JavaScript?

Export the function from the other module with the 'export' keyword and import the function
to the original module like: import {function} from 'othermodule.js'.

### Functional

#### 32. What is recursion?

Recursion is a method where a function calls itself once or more in its body.

#### 33. Write a recursive function which calculates the Fibonacci numbers!

def fibo_num(i):
if i <= 1:
return i
else:
return(fibo_num(i-1) + fibo_num(i-2))

#### 34. How to store a function in a variable in Python?

Define the function:

```python
def my_func(i):
print(i)
```

Address the function to a variable:

```python
my_var = my_func
```

You can call the function with the variable:
my_var(10) --- prints 10

#### 35. List the ways of defining a callable logical unit in JavaScript!

as ordinary function, as arrow function, assign a function to the property of an object
and call it as a method via that object

#### 36. What is an event listener? How to attach one?

Event listeners are meant to determine which item of the html should react to what type of event
and what function should it trigger. Event listeners can be attached in javascript to dom elements
by the addEventListener built-in function.

#### 37. How to trigger an event in JavaScript?

With the dispatchEvent function.

#### 38. What is a callback function? Tell some examples of its usage.

A callback function is an executable code that can be passed as the argument of another
function which executes the callback function. For e.g.: the built-in setTimeout function

#### 39. What is a Python decorator? How does it work? Tell some examples of its usage.

A decorator takes in a function, adds some functionality and returns it without permanently modifying it.
For e.g.: in Flask the app.route is used as decorator.

#### 40. What is the difference between synchronous and asynchronous execution?

When a piece of code is executing synchronously, the program waits for it to finish before moving to the next task.
With asynchronous execution tasks will be executed regardless of the other tasks finish time.

## Programming languages

### SQL

#### 41. How can you connect your application to a database server? What are the possible ways?

For example with the help of psycopg2.

#### 42. When do you use the DISTINCT keyword in SQL?

When you want to get only the unique values of a table.

#### 43. What are aggregate functions in SQL? Give 3 examples.

Aggregate functions are meant to group together values of multiple rows based on some kind of criteria.
For e.g.: COUNT(), AVG(), SUM()

#### 44. What kind of JOIN types do you know in SQL? Could you give examples?

left join, right join, inner join, outer join, full join

#### 45. What are the constraints in sql?

Constraints are rules that apply to data in a certain column of a table.
For e.g.: you can determine if a column should only consist of integers or be unique etc.

#### 46. What is a cursor in SQL? Why would you use one?

An SQL cursor is meant to retrieve data one row at a time.
It is best to use cursors to update data row by row in a table.

#### 47. What are database indexes? When to use?

Indexes are used to speed up data retrieval from a database.
The index keys are based on the table's columns.
It is useful when we want to select some values of a large database.

#### 48. What are database transactions? When to use?

A transaction is a unit of work that is performed against a database.
Transactions are units or sequences of work accomplished in a logical order,
whether in a manual fashion by a user or automatically by some sort of a database program.

#### 49. What kind of database relations do you know? How to define them?

One to One Relationships
One to Many and Many to One Relationships
Many to Many Relationships
Self Referencing Relationships

#### 50. You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?

```Postgre
SELECT \* FROM table WHERE address LIKE '%Miskolc%';
```

#### 51.How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?

I would create a table which would store the deleted/original version data.

### HTML & CSS

#### 52. What’s the difference between XML, XHTML and HTML?

XHTML is HTML written as XML.
XHTML is very similar to HTML, but it is stricter.
While HTML runs on the major browsers while containing 'bad' practices
(for e.g.: not closed elements, missing '<!DOCTYPE ....>'),
XHTML needs to contain everything according to rules.

#### 53. How to include a JavaScript file in a webpage?

in the hesd tag: '<script src={path/to/file.js}></script>'

#### 54. How to include a CSS file in a webpage?

in the head tag: '<link rel="stylesheet" href="{path/to/file.css">'

#### 55. How to select an element using its id in CSS?

With a hashtag and the id name, like: #id-name

#### 56. How to select elements using their class in CSS?

Dot and the name of the class, like: .class-name

#### 57. How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?

.alpha.beta{ }

#### 58. How to select all list items in all ordered lists on the page in CSS?

ol li{ }

#### 59. How to select elements using their attributes in CSS?

[attribute='value']

#### 60. What are UX and UI?

UX: user experience, the user's interaction or experience with the product
UI: user interface, focuses on the user's visual experience

#### 61. Please list some points that an application should fulfill to have good UX.

Clear and readable, nice design, use familiar elements, user friendly

#### 62. What is XML, XSLT, DTD?

XML: stands for eXtensible Markup Language, it was designed to store and transport data,
it is both human- and machine-readable
XSLT: eXtensible Stylesheet Language Transformations, it is the recommended style sheet language for XML
DTD: Document Type Definition, it defines the structure and the legal elements and attributes of an XML document

#### 63. What is the difference between HTML and XML?

XML is meant to carry data based on what the data is, while HTML's purpose is to display data based on how it looks.

### Javascript

#### 64. What is javascript?

It is a programming language used to run codes on the browser (client) side of the program.

#### 65. When to use AJAX? Bring examples of its usage.

AJAX stands for Asynchronous JavaScript and XML. With AJAX the data on a webpage can be modified without
refreshing the whole page. For e.g.: Facebook uses AJAX to load new posts on your timeline.

#### 66. What is DOM and how to manipulate it from Javascript?

DOM is Document Object Model. It basically represents the internal of the page.
With DOM manipulation we can choose a document element (by class, ba tag, by id)
and modify its content or style, or we can create or delete elements.

#### 67. What are events and how/why to use them in Javascript?

HTML and Javascript interacts with each other through events which are usually triggered by the user
on the browser. For e.g.: user clicks on a button, user presses a key, etc.
JS can react to these events with eventHandlers.

#### 68. What is event bubbling/capturing? How would you use it?

When an event happens on an element, it first runs the handlers on it, then on its parent,
then all the way up on other ancestors. Event Capturing is when the event starts from top element
to target element.

#### 69. What is JSON and how do we use it?

JSON (JavaScript Object Notation) is an open standard file format, and data interchange format,
that uses human-readable text to store and transmit data objects consisting of attribute–value pairs
and array data types (or any other serializable value). It is a very common data format,
with a diverse range of applications, such as serving as replacement for XML in AJAX systems.

## Software engineering

### Version control

#### 70. What type of branching strategy would you use?

Git flow workflow. I would create a Develop branch from the master and a new branch for each feature from the Develop branch.

#### 71. What would you do if you find a bug on the production code (master branch)?

I would open a new branch and fix the bug on it and then make a pull request. Or find a version in the commits that is bug-free.

#### 72. How can you move changes from one branch to another in GIT?

With a pull request (hopefully after a successful merge/rebase).

#### 73. How does a VCS help with code reviews?

We can see who developed and what feature through each commit. It is also easier to catch the cause of a bug.

#### 74. What is your favorite git command? Why?

git commit --amend, because you can easily add some additional changes to a commit.

#### 75. What does remote/local mean in Git?

Respositories/branches are local when they are only available on your local computer. Remote repos/branches are a version of your project that is hosted on the Internet (for e.g.: github) or some kind of network.

### DevOps

#### 76. Why is it good to use a package manager software?

It eliminates the need for manual installs and updates, it provides centralized distribution and hosting,it lets you know the library versions you’re using, it helps prevent incompatible files from mixing Together

#### 77. Why is it good to use a virtual environment for a project?

The main purpose of Python virtual environments is to create an isolated environment for Python projects. This means that each project can have its own dependencies, regardless of what dependencies every other project has.

### Networks

#### 78. What kind of HTTP status codes do you know?

1xx: Informational response, 2xx: Success, 3xx: Redirection, 4xx: Client error, 5xx: Server error

#### 79. What is a API?

API is the acronym for Application Programming Interface, which is a software intermediary that allows two applications to talk to each other.

#### 80. What is REST API? !!!!

A RESTful API is an application program interface (API) that uses HTTP requests to GET, PUT, POST and DELETE data. A RESTful API -- also referred to as a RESTful web service or REST API -- is based on representational state transfer (REST) technology, an architectural style and approach to communications often used in web services development.

#### 81. What is JSON? When to use? !!!!!

JSON (JavaScript Object Notation) is an open standard file format, and data interchange format, that uses human-readable text to store and transmit data objects consisting of attribute–value pairs and array data types (or any other serializable value). It is a very common data format, with a diverse range of applications, such as serving as replacement for XML in AJAX systems.

#### 82. What is TCP/IP? What layers does it define, what are they responsible for? !!!!!

TCIP/ IP iss the conceptual model and set of communications protocols used in the Internet and similar computer networks.
Process/Application Layer: It is responsible for handling high-level protocols, issues of representation.
Host-to-Host/Transport Layer: The transport layer is responsible for the reliability, flow control, and correction of data which is being sent over the network.
Internet Layer: The main responsibility of the internet layer is to send the packets from any network, and they arrive at the destination irrespective of the route they take.
Network Access/Link Layer: This layer is mainly responsible for the transmission of the data between two devices on the same network.

#### 83. What’s the difference between TCP and UDP? !!!!

Transmission Control Protocol (TCP) is a connection-oriented protocol that computers use to communicate over the internet. It is one of the main protocols in TCP/IP networks. TCP provides error-checking and guarantees delivery of data and that packets will be delivered in the order they were sent.

User Datagram Protocol (UDP) is a connectionless protocol that works just like TCP but assumes that error-checking and recovery services are not required. Instead, UDP continuously sends datagrams to the recipient whether they receive them or not.

#### 84. How does an HTTP Request look like? What are the most relevant HTTP header fields? !!!!!

Start line: an http method, the request target (usually an url), http version
Headers: general headers, request headers, entity headers
Body

#### 85. How does an HTTP Response look like? What are the most relevant HTTP header fields?

Status line: protocol version, status code, status text
Headers: general headers, response headers, entity headers
Body

#### 86. What is DNS? How does it work?

DNS (Domain Name System) translates domain names to IP addresses so browsers can load Internet resources.

#### 87. What is a web server? !!!

Web server can refer to hardware or software, or both of them working together. A web server processes incoming network requests over HTTP and several other related protocols. The primary function of a web server is to store, process and deliver web pages to clients.

#### 88. Explain the client-server architecture.

The client-server architecture describes the relationship of cooperating programs in an application. The server component provides a function or service to one or many clients, which initiate requests for such services.

#### 89. What would you use a session for?

Session is often used to keep a user logged in on a webpage, so they don't have to log in after every refresh. This data is stored on the server side, so -- unlike cookies -- the user cannot modify it.

#### 90. What would you use a cookie for?

Cookie is a small piece of data sent from a website and stored on the user's computer by the user's web browser while the user is browsing. Since it is stored on the client side, it can be deleted or modified by the user or the user can disable the whole cookie feature in the user's browser. It is usually used to store preferences of the user.

## Software Development Methodologies

#### 91. What kind of software development methodologies do you know? What are the main features of these?

Waterfall Project Management, Agile Project Management

#### 92. What are the SCRUM roles?

ScrumMaster, Product Owner (PO), Scrum Team

#### 93. What are the SCRUM ceremonies?

Sprint Planning Meeting, Daily Standups, Retrospective, Sprint Review Meeting, Project Retrospective meeting

#### 94. What are the SCRUM artifacts?

the product, product backlog, sprint backlog, sprint burndown chart, release burndown chart

#### 95. What is the main goal of a retrospective meeting?

The main goal of the retrospective meeting is to evaluate the latest sprint, identify the good and bad practices and improve future sprints.

#### 96. Explain, when would you recommend to use the waterfall methodology?

The waterfall project is suitable for shorter projects, which includes clear requirements and there is a low possiobility that the project scope would change.
