# Readings: Express, NPM, TDD, CI/CD

## Reading

### An Introduction to Node.js and Express

[An Introduction to Node.js and Express](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction)

#### 1. Explain middleware as though I were a non-technical recruiter.

Middleware is software that works between a user’s request and the server’s response. It may check login information, process data, record activity, or handle errors.

Middleware can be compared to a receptionist who checks each visitor and directs them to the correct office.

#### 2. Express is the most popular _____.

Express is the most popular **Node.js web framework**.

#### 3. Express is “unopinionated.” What does that mean?

Express does not require developers to organize an application in one specific way. Developers can choose the tools, libraries, and file structure that work best for their project.

#### 4. What is a module, and why is modularity useful to developers?

A module is a reusable file or package containing related code. Modularity divides a large application into smaller parts that are easier to understand, test, debug, maintain, and reuse.

## NPM

[What is NPM?](https://docs.npmjs.com/about-npm)

NPM is a package manager for JavaScript. It allows developers to find, install, update, and manage reusable packages of code.

#### 1. What version of NPM are you running on your machine?

Run the following command in the terminal:

```bash
npm -v
```

My NPM version is: `____________`

#### 2. What command installs a package called `jshint`?

```bash
npm install jshint
```

Because JSHint is normally used during development, it can also be installed as a development dependency:

```bash
npm install --save-dev jshint
```

## Test-Driven Development

[What is TDD?](https://www.agilealliance.org/glossary/tdd/)

Test-Driven Development, or TDD, is a process in which developers write a test before writing the code needed to pass that test.

#### 1. Explain why tests are important as though I were your non-technical elder.

Testing software is similar to checking a smoke alarm before there is a fire. Tests confirm that the software works correctly and warn developers when a change causes something to break.

#### 2. What are three expected benefits of testing?

- Testing reduces the number of bugs.
- Testing helps developers discover problems earlier.
- Testing allows developers to change code with greater confidence.

#### 3. Name at least two individual and two team pitfalls.

**Individual pitfalls:**

- Forgetting to run tests regularly.
- Writing tests that are too large or complicated.

**Team pitfalls:**

- Only some team members consistently write tests.
- The team fails to maintain or regularly run the test suite.

## CI/CD

[CI/CD](https://www.youtube.com/watch?v=k2aNsQKwyOo)

#### 1. What are three benefits of Continuous Integration?

- Bugs and conflicts are discovered earlier.
- Automated tests provide faster feedback.
- Small code changes are easier and safer to combine.

#### 2. What is the difference between Continuous Delivery and Continuous Deployment?

**Continuous Delivery** automatically tests and prepares code for release, but a person makes the final decision to publish it.

**Continuous Deployment** automatically publishes every code change that passes the required tests.

#### 3. How does GitHub fit into this process?

GitHub provides a shared location where a development team can store and review its code. It is similar to a shared workspace that keeps a history of every change.

When developers send their changes to GitHub, GitHub Actions can automatically build and test the application. If the tests pass, the code can be prepared for release or deployed automatically.

## Bookmark and Review

- [Node.js documentation](https://nodejs.org/en/docs/)
- [NPM documentation](https://docs.npmjs.com/)
- [Express documentation](https://expressjs.com/en/4x/api.html)
- [HTTP status codes](https://www.restapitutorial.com/httpstatuscodes.html)
- [SuperTest](https://github.com/forwardemail/supertest)

## Reflection

#### What are your learning goals after reading and reviewing the class README?

My learning goals are to understand how to build an Express server, use middleware, organize applications with modules, write tests using TDD, and use GitHub to automate testing and deployment.