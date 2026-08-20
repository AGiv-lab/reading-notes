# Express, NPM, TDD, and CI/CD Notes

## Express

Express is a web framework used with Node.js to create servers and APIs.

### Middleware

Middleware is code that runs between a request and a response. It can:

- Process data
- Check authentication
- Record activity
- Handle errors

Middleware is similar to a receptionist who checks and directs visitors.

### Unopinionated Framework

Express is unopinionated because it does not require one specific project structure. Developers can choose how to organize their application.

### Modules

A module is a reusable file or package containing related code.

Modules make code easier to:

- Organize
- Understand
- Test
- Debug
- Maintain
- Reuse

## NPM

NPM is a package manager for JavaScript. It helps developers install and manage packages.

Check the installed NPM version:

```bash
npm -v
```

Install JSHint:

```bash
npm install jshint
```

Install JSHint as a development dependency:

```bash
npm install --save-dev jshint
```

## Test-Driven Development

Test-Driven Development, or TDD, means writing tests before writing the application code.

### TDD Process

1. Write a test that fails.
2. Write enough code to pass the test.
3. Improve the code.
4. Repeat.

### Benefits of Testing

- Finds bugs earlier
- Reduces errors
- Makes code changes safer

### Testing Pitfalls

**Individual pitfalls:**

- Forgetting to run tests
- Writing tests that are too complicated

**Team pitfalls:**

- Not everyone writes tests
- The test suite is not maintained

## Continuous Integration

Continuous Integration, or CI, means regularly combining code changes and automatically testing them.

### Benefits of CI

- Finds problems earlier
- Provides faster feedback
- Makes code easier to combine

## Continuous Delivery

Continuous Delivery automatically tests and prepares code for release. A person decides when to publish it.

## Continuous Deployment

Continuous Deployment automatically publishes code after it passes all required tests.

## GitHub and CI/CD

GitHub stores and tracks a team’s code. GitHub Actions can automatically build, test, and deploy an application when new code is pushed.

## Learning Goals

My goals are to learn how to:

- Build an Express server
- Use middleware
- Organize code with modules
- Write automated tests
- Understand TDD
- Use GitHub for CI/CD