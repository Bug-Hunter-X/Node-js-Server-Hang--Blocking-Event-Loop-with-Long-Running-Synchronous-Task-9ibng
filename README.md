# Node.js Server Hang: Blocking Event Loop

This repository demonstrates a common Node.js issue where a long-running synchronous operation in a request handler blocks the event loop, causing the server to hang and become unresponsive.  The `server.js` file contains the buggy code, and `serverSolution.js` provides a solution using asynchronous operations. 

## Problem

The problem lies in the synchronous `while` loop within the request handler. This loop keeps the CPU busy for 5 seconds, preventing the event loop from processing other requests or events.  As a result, the server appears to hang and new requests are not processed promptly or at all.

## Solution

The solution involves replacing the synchronous operation with an asynchronous approach, allowing the event loop to continue processing other tasks concurrently.  The `serverSolution.js` demonstrates this by using `setTimeout` to simulate the long running task asynchronously.