# Node.js Server Unresponsiveness with Long-Running Requests

This repository demonstrates a common issue in Node.js servers: unresponsiveness caused by long-running operations within request handlers.  When a request handler takes a significant amount of time to process, it blocks the event loop, preventing the server from handling other requests. This leads to a hung or unresponsive server.

The `bug.js` file shows the problematic code. The `bugSolution.js` file provides a solution using asynchronous operations to prevent blocking.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`.
4. Make multiple requests to `http://localhost:3000`. You'll observe that after the first request, subsequent requests will hang until the first request completes.

## Solution

The solution uses asynchronous methods such as `setTimeout` and promises to avoid blocking the event loop.  This ensures that other requests can be processed while long-running operations are underway.