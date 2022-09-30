# Fri Sep 30 Reading Notes

## [What are JavaScript Promises & How to Use them](https://javascript.plainenglish.io/what-are-javascript-promises-how-to-use-them-84fdff5757b9)

### What are Promises, and why use them?

**Callback** **functions**

The first solution was to tell the browser: "Run his process (for example, call this API), and when it's done, let me know". Or more precisely: on completion execute the function provided (as a parameter in a function call). This function we want the code to call back is what is called a "callback".

The callback function allows us to add further logic in reaction to the server's response. For example: when the user clicks on the button, first log in by calling the login API. When the server responds, retrieve the authentication data and interpret it. Then call a web service with the login data to update the player's information.

There are three callbacks described above. The first responds to the button press. The second manages the call and response to the login API. And the last one retrieves the response from the second web service.

What happens when error handling comes to play.

Imagine having specifying processing to carry out at each stage or depth of the callback stack. Now imagine an error occurs. If it is not managed with a try/catch, the error message is useless, calling it out at line 5 of the anonymous function.

The best solution is to add try/catch management at every depth, on every callback call. This quickly becomes *very* unwieldy.

### A Promise

A promise has three fundamental properties:

  1. It encapsulates asynchronous processing
  2. It can be chained, without the need to nest (callback) functions
  3. It handles errors

The object of the Promise, is that it has two functions that can be called on it: "then" and "catch". The "then" function takes the result of the resolution as a parameter, and returns a new promise. The "catch" function takes the *error* as a parameter and also returns a new promise.

```javascript
  p
  .then(function1)
  .then(function2)
```

`p` is a promise. Chaining allows us to read code sequentially, instead of diving deeper and deeper into nested callback functions.

Promises trigger the first "catch" regardless of which steps throws an error. This allows centralized (and sane!) error management.

### Let's make a Promise

Coding a function that creates a promise that waits for a specified time.

The Promise's constructor takes a function.

This function takes two functions as parameters, typically called "resolve" and "reject". We call these when the process ends. Either it succeeds, in which case we call "resolve", or it fails and we call "reject".

The sleep function looks like this:

```javascript
const sleep = (nb) => {
  return new Promise ((resolve, reject) => {
    setTimeout(() => resolve(), nb);
  })
};
```

Second parameter, reject, is not being used here. Leaving it to be complete.

Now if we do:

```javascript
sleep(1000).then(() => console.log("done"));
```

Sleep produces a promise that triggers a function after a certain time.

Another `Promise` sequence that uses the sleep promise.

```javascript
const wait = () => {
  sleep(1000)
  .then(() => sleep(1000))
  .then(() => console.log("2s later"));
};
```

Similar to async/await notation:

```javascript
const wait = async () => {
  await sleep(1000);
  await sleep(1000);
  console.log("2s later");
};
```

The only difference is in the syntax. The same Promise objects are being called. If we wrap the two await calls in a try/catch, it will handle errors just like synchronous code does.

#### Sum it up

JavaScript is all about interacting with interfaces and APIs. Callbacks used to be the preferred way of doing this, but they have many drawbacks. Promises are a far better solution. The async/await syntax uses Promises to describe asynchronous behavior while staying readable, and alow us to escape "callback hell".

## Things I want to know more about

[<---BACK](README.md)
