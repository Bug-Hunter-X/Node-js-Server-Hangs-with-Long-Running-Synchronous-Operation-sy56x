# Node.js Server Hang: Synchronous Operation Blocking Event Loop

This repository demonstrates a common issue in Node.js where a long-running synchronous operation within the HTTP request handler blocks the event loop, causing the server to become unresponsive.

## The Problem

The `bug.js` file contains a simple HTTP server.  However, the request handler includes a `while` loop that simulates a long-running task. This synchronous operation blocks the event loop, preventing the server from processing other requests or responding to existing ones.

## The Solution

The `bugSolution.js` file presents a solution using asynchronous operations (e.g., `setTimeout` or promises/async/await).  By offloading the long-running task to an asynchronous context, the event loop remains free to handle other requests and the server doesn't hang.