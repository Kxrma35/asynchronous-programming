# Asynchronous Programming in JavaScript
## Overview
JavaScript is single‑threaded, meaning it executes one task at a time.
Asynchronous programming allows tasks to run without blocking the main thread, making applications faster and more responsive.

## Why Asynchronous?
Blocking code: Long tasks (like API calls) freeze the UI.

Non-blocking code: Lets other tasks continue while waiting.

Common use cases:

Fetching data from APIs

File uploads/downloads

Timers (setTimeout, setInterval)

## The Event Loop
Call stack: Executes functions in order.

Web APIs: Handle async tasks (timers, fetch).

Callback queue: Stores completed async tasks.

Event loop: Moves tasks from queue to stack when ready.

## Callbacks
A callback is a function passed into another function to run later.

js
setTimeout(() => {
  console.log("Hello after 2 seconds");
}, 2000);
## Problem: Callback hell — deeply nested callbacks become hard to read and maintain.

## Promises
A Promise represents a future value.

States: pending, fulfilled, rejected

js
fetch("data.json")
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));
## Async/Await
async: Declares a function returns a Promise.

await: Pauses execution until Promise resolves.

js
async function getData() {
  try {
    const response = await fetch("data.json");
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}
## Real-World Use Cases
API requests

File uploads/downloads

Animations and timers

Chat applications

## Best Practices
Prefer async/await for readability.

Always handle errors (try...catch or .catch()).

Avoid deeply nested callbacks.

Keep async functions modular.

## Summary
Asynchronous programming prevents blocking.

Tools evolved: Callbacks → Promises → Async/Await.

Mastering async makes apps faster and more user‑friendly.
