# Unresponsive Node.js Server

This repository demonstrates a common Node.js issue: an unresponsive server caused by a long-running synchronous operation within the request handler. The `bug.js` file contains the problematic code.  The solution (`bugSolution.js`) shows how to refactor the code using asynchronous operations to prevent blocking the event loop.

## Problem

Node.js uses an event-driven, non-blocking I/O model.  However, if a request handler performs a long-running synchronous operation, it blocks the event loop, preventing the server from handling subsequent requests.  This results in an unresponsive server.

## Solution

The solution involves refactoring the code to use asynchronous operations or offloading the long-running task to a worker thread or a separate process. This prevents blocking the main event loop and maintains server responsiveness.