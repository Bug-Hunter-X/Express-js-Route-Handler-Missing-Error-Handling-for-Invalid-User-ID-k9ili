# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, the example code attempts to parse a user ID from the request parameters without checking if it's a valid integer. This can lead to unexpected crashes or incorrect behavior.

## Bug Description

The `bug.js` file contains an Express.js route handler that fetches a user by ID. However, it lacks error handling for cases where the `userId` parameter is not a valid integer.  If a non-numeric value is passed, `parseInt(userId)` will return `NaN`, leading to the `users.find` method failing silently or throwing an error depending on the `users` array implementation. 

## Bug Solution

The `bugSolution.js` file provides a corrected version of the route handler. This improved version includes explicit checks to ensure the `userId` is a valid integer before attempting to access the user data. This prevents unexpected errors and improves the overall robustness of the application.