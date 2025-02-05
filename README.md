# Node.js Server Unresponsiveness Due to Long-Running Requests

This repository demonstrates a common issue in Node.js applications where the server becomes unresponsive due to long-running requests that block the event loop. The `bug.js` file contains code that simulates a long-running request, causing the server to hang. The `bugSolution.js` file demonstrates how to resolve the issue by using asynchronous operations and employing proper error handling techniques.

## Description

Node.js is single-threaded and relies on the event loop to handle asynchronous operations. If a request handler executes a long-running synchronous operation, it blocks the event loop, preventing other requests from being processed. This leads to server unresponsiveness and performance degradation.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory in your terminal.
3. Run `node bug.js`.
4. Send a request to `http://localhost:3000`. Note that the server will become unresponsive for 5 seconds.

## Solution

The key to solving this problem is to prevent long-running operations from blocking the event loop. This can be done using asynchronous operations (e.g., using Promises, async/await) or by offloading long-running tasks to worker threads or other processes.  Proper error handling is also crucial.