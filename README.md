# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input. Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer without verifying its numeric nature. This can lead to unexpected behavior or crashes if a non-numeric ID is provided.

## Bug Description
The `bug.js` file contains a route handler that fetches a user by ID.  It directly parses the `id` parameter as an integer using `parseInt()` without any checks to ensure that the parameter is actually a valid integer.  If a non-numeric value is provided, `parseInt()` will return `NaN`, leading to errors further down the line.

## Solution
The `bugSolution.js` file demonstrates a corrected version of the route handler that includes error handling.  It first checks if the `id` parameter is a valid number using `isNaN()`.  If not, it returns a 400 Bad Request error.  Otherwise, it continues with the user lookup.

## How to Run
1. Clone this repository.
2. Navigate to the repository's directory.
3. Install the required packages: `npm install express`
4. Run the buggy code: `node bug.js`
5. Test with a valid ID and then an invalid ID (e.g., 'abc'). Observe the behavior.
6. Run the fixed code: `node bugSolution.js`
7. Test again with a valid ID and an invalid ID. Observe the improved behavior.