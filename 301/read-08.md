##APIs Notes
*What is an API?*

**An API (Application Programming Interface) allows two programs to communicate with each other.**

-Example
-React App → API → Weather Data

**The React app asks for information and the API sends information back.**

###Backend Connection

-The backend often acts as the middleman:

-Frontend → Backend → Third-Party API

-Instead of exposing API keys to users, the backend makes the request safely.

*Why Do We Need a Server?*

**A server helps us:**

-Hide API keys
-Process data before sending it to the frontend
-Handle errors
-Connect to databases
-Communicate with third-party APIs
-Backend Connection

*Think of the backend as a restaurant kitchen:*

-Customer = Frontend
-Kitchen = Backend
-Food Supplier = Third-Party API

*The customer doesn't talk directly to the supplier. The kitchen handles everything.*

**What Do We Keep in a .env File?**

*A .env file stores sensitive information.*

**Examples**
-API_KEY=abc123
-PORT=3001
-DATABASE_URL=mydatabase
-Backend Connection

*Backend developers use .env files to keep secrets out of GitHub repositories.*

**Never commit API keys to GitHub.**

*Why Restart Nodemon After Changing .env?*

-Nodemon automatically watches most files.

-However, when .env changes, Node must reload the environment variables.

###Backend Connection

-The server reads environment variables when it starts.

-If those values change, the server needs a restart.

**True or False: All APIs Require a Key?**

**False**

###Some APIs:

-Require keys
-Require authentication
-Are completely public
*Examples*
-Weather APIs often require keys.
-Some public datasets do not.

## How do you make an API call in the server using axios?

1. Create a URL for the API endpoint.
2. Use `axios.get()` to send a request to that URL.
3. Use `await` to wait for the response.
4. Access the returned data through the `.data` property.

Example:

```javascript
const url = `http://urlToAPI/?key=${process.env.MY_API_KEY}&city=seattle`;

const axiosResults = await axios.get(url);

console.log(axiosResults.data);

*Backend Connection

-One common backend responsibility is securely managing API keys.

###Using Axios to Call an API

*Example:*

-const url = `http://urlToAPI/?key=${process.env.MY_API_KEY}&city=seattle`;

-const axiosResults = await axios.get(url);

-console.log(axiosResults.data);
-What Happens?
-Build the URL.
-Send a request.
-Wait for the response.
-Access the data.

*The function must be marked async because await is being used.*
-axios returns a large response object.
-The information we usually want is found in response.data.

*Backend Connection*

-This is one of the most common backend tasks:

-Receive request from frontend
↓
-Call third-party API with axios
↓
-Receive data
↓
-Format data
↓
-Send response to frontend
Important Reminder About Axios

-Axios returns a large response object.

**Example:**

**const response = await axios.get(url);**

*The useful information is usually found in:*

-response.data
-Backend Connection

*Most backend API routes follow this pattern:*

-const response = await axios.get(url);

-res.send(response.data);

-The backend fetches data from somewhere else and then passes it along to the frontend.


#Discussion

**Readings: APIs**
1. *What does REST stand for?*

**Representational State Transfer**

*2. REST APIs are designed around a ____________.*

**Resource**

Examples:

User
Product
Weather forecast

*3. What is an identifier of a resource? Give an example.*

**A resource identifier is a URI (Uniform Resource Identifier) that uniquely identifies a resource.**

Example:

/users/123

This identifies user 123.

4. What are the most common HTTP verbs?
GET
POST
PUT
PATCH
DELETE

Quick Reference
Verb	Purpose
GET	Retrieve data
POST	Create data
PUT	Update/replace data
PATCH	Update part of data
DELETE	Remove data


5. What should the URIs be based on?

**URIs should be based on nouns (resources) rather than actions.**

Good:

/users

Bad:

/getUsers


6. Give an example of a good URI.
/api/customers/5/orders

or

/users/123

These clearly identify resources.

7. What does it mean to have a "chatty" web API? Is this a good or bad thing?

**A chatty API requires many requests to get the needed data.**

Example:

Request 1 → User
Request 2 → Orders
Request 3 → Address
Request 4 → Payment Info

This is generally considered bad because it creates extra network traffic and slows applications down.

8. *What status code does a successful GET request return?*
**200 OK**

9. *What status code does an unsuccessful GET request return?*

**Common examples:**

404 Not Found
400 Bad Request

**Most commonly:**

*404 Not Found*
*500s server side issues*


10. What status code does a successful POST request return?
201 Created


11. What status code does a successful DELETE request return?
204 No Content

This means the resource was successfully deleted and there is no content to return.

####Backend Connection Notes

REST APIs are one of the main ways frontends and backends communicate.

Typical flow:

React Frontend
      ↓
GET /weather
      ↓
Express Backend
      ↓
Weather API
      ↓
Data returned to frontend

Key ideas:

Resources are represented by URIs.
HTTP verbs describe actions.
Status codes tell whether a request succeeded or failed.
REST APIs help keep communication between systems organized and predictable.

**GET    = Read**
-POST   = Create
*PUT    = Replace*
-PATCH  = Edit
**DELETE = Remove**

## API Design Best Practices - Brief Summary

This article explains how to design REST APIs so they are easy to understand, use, and maintain.

### Key Takeaways

- REST APIs are built around **resources** (such as users, products, or orders).
- Resources should be identified using clear **URIs**.
- URIs should use **nouns**, not verbs.
- Use standard **HTTP methods**:
  - GET → retrieve data
  - POST → create data
  - PUT/PATCH → update data
  - DELETE → remove data
- APIs should return appropriate **HTTP status codes** to indicate success or failure.
- Avoid creating "chatty" APIs that require many requests to retrieve related data.
- Responses should be organized and consistent so developers know what to expect.
- API design should focus on simplicity, scalability, and ease of use.

### Why It Matters

Good API design makes it easier for frontend and backend applications to communicate. Well-designed APIs are easier to build, test, maintain, and expand as applications grow.

## RegExr - Quick Summary

RegExr is an interactive website for learning, testing, and building regular expressions (RegEx).

### What is RegEx?

Regular Expressions (RegEx) are patterns used to search, match, and validate text.

Examples:

- Find email addresses
- Validate phone numbers
- Search for specific words
- Replace text patterns

### Useful Cheatsheet Symbols

| Symbol | Meaning |
|----------|----------|
| `.` | Any single character |
| `\d` | Any digit (0-9) |
| `\w` | Any letter, number, or underscore |
| `\s` | Any whitespace character |
| `+` | One or more |
| `*` | Zero or more |
| `?` | Optional |
| `^` | Start of string |
| `$` | End of string |
| `[abc]` | Match a, b, or c |
| `[^abc]` | Match anything except a, b, or c |

### Why Use RegEx?

RegEx helps developers:

- Validate user input
- Search text efficiently
- Extract information from strings
- Clean and format data

### Backend Connection

RegEx is commonly used on servers to validate incoming data before saving it to a database.

Examples:

- Checking email format
- Validating ZIP codes
- Ensuring passwords meet requirements
- Parsing API responses

-[Regex Tutorial](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285){:target="_blank"}
Regex Tutorial - Quick Summary
Regex Tutorial (Medium Cheatsheet)

This tutorial introduces Regular Expressions (RegEx) through simple examples and common patterns.

Key Takeaways
RegEx is used to search and match text patterns.
Special characters have specific meanings.
Quantifiers control how many matches are allowed.
Character classes help match groups of characters.
Common Patterns
Pattern	Meaning
\d	Any digit
\w	Letter, number, or underscore
\s	Whitespace
+	One or more
*	Zero or more
?	Optional
{n}	Exactly n times
{n,m}	Between n and m times
Common Uses
Email validation
Phone number validation
Password requirements
Finding and replacing text

-[Regex 101](https://regex101.com/){:target="_blank"}
# Regex101 - Quick Summary

Regex101 is an online RegEx testing and debugging tool.

### Key Features

- Test RegEx patterns in real time
- See matches highlighted instantly
- View explanations for each pattern
- Debug and improve expressions
- Learn RegEx interactively

### Why It's Useful

Instead of guessing whether a RegEx works, you can:

1. Enter sample text
2. Enter a RegEx pattern
3. See exactly what matches

### Example

Pattern:

```regex
\d+

Text:

Order #123 contains 5 items

Matches:

123
5

*Backend Connection*

*Developers often use Regex101 to build and test validation rules before adding them to applications.*

Examples:

Form validation
API input validation
Data cleaning
Log file analysis
Quick Memory Tip
RegExr = Learn and practice RegEx
Regex101 = Test and debug RegEx

Both tools are commonly used when working with user input, APIs, and backend validation.
1. Recognize when RegEx can solve a problem.
2. Use a cheatsheet.
3. Test the pattern in Regex101.
4. Add it to your code.
