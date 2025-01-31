# Express.js JSON Body Parsing Issue
This repository demonstrates a common issue encountered when working with JSON request bodies in Express.js applications.  The problem arises when the `express.json()` middleware is not properly configured or used, leading to the request body being parsed incorrectly or not being parsed at all.

## Bug Description
The provided Express.js server uses the `express.json()` middleware to parse incoming JSON data. However, when a POST request with a JSON body is sent to the `/data` endpoint, `req.body` remains undefined, causing the server to fail to process the request correctly. This often leads to unexpected errors, unexpected behaviour, or silent failure.

## Solution
The solution involves ensuring that `express.json()` middleware is correctly placed in the middleware stack *before* any route handlers that expect a JSON body.  Double-check the order of middleware functions.