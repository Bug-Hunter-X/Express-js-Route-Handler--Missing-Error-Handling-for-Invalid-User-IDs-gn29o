# Express.js Route Handler: Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the `/users/:id` route does not handle cases where `:id` is not a valid integer.

The `bug.js` file contains the flawed code.  The `bugSolution.js` file provides a corrected version with robust error handling.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install express`.
3. Run `node bug.js`.
4. Send a GET request to `/users/abc` (or any non-numeric ID).

The original code will likely crash or throw an error because `parseInt('abc')` returns `NaN`, causing problems when comparing to numbers in the `users` array.  The solution implements proper error handling to prevent this.