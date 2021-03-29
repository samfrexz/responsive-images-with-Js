# responsive-images-with-Js

Explanation of SetTimeout JavaScript with examples

setTimeout is a native JavaScript function (although it can be used with a library such as jQuery, as we’ll see later on), which calls a function or executes a code snippet after a specified delay (in milliseconds). This might be useful if, for example, you wished to display a popup after a visitor has been browsing your page for a certain amount of time, or you want a short delay before removing a hover effect from an element (in case the user accidentally moused out).

Example of SetTimeout

```js
sayMyName = () => {
  console.log(`i'm Samfrexz the great!`); //I'm samfrexz the great! will be the output after 2secs
};
setTimeout(sayMyName, 2000);
```

Explanation of Promise with example

A promise is a special JavaScript object that links the “producing code” and the “consuming code” together.
A "Producing code" is code that can take some time.
A "Consuming code" is code that must wait for the result.

The syntax for promise can be seen below:

```js
let promise = new Promise(function (resolve, reject) {
  // executor (the producing code)
});
```

When the executor obtains the result, be it soon or late, doesn’t matter, it should call one of these callbacks:

resolve(value) — if the job finished successfully, with result value.
reject(error) — if an error occurred, error is the error object

Example:

```js
const posts = [
  { title: 'post one', body: 'this is post one' },
  { title: 'post two', body: 'this is post two' }
];

function getPosts() {
  setTimeout(() => {
    let output = '',
    posts.forEach((post, index) => {
      output += `<li>${post.title}</li>`;
    });
    document.body.innerHtml = output;
  }, 1000);
}
```

```js
function createPost(post) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      posts.push(post);

      const error = false;

      if (!error) {
        resolve();
      } else {
        reject("error: something went wrong");
      }
    }, 2000);
  });
}

createPost({ title: "post three", body: "this is post three" }).then(getPosts);
```

Explanation of Side Effect

Side Effects
A side effect is any application state change that is observable outside the called function other than its return value. Side effects include:
Modifying any external variable or object property (e.g., a global variable, or a variable in the parent function scope chain)
Logging to the console
Writing to the screen
Writing to a file
Writing to the network
Triggering any external process
Calling any other functions with side-effects
Side effects are mostly avoided in functional programming, which makes the effects of a program much easier to understand, and much easier to test.
Haskell and other functional languages frequently isolate and encapsulate side effects from pure functions using monads. The topic of monads is deep enough to write a book on, so we’ll save that for later.
What you do need to know right now is that side-effect actions need to be isolated from the rest of your software. If you keep your side effects separate from the rest of your program logic, your software will be much easier to extend, refactor, debug, test, and maintain.
This is the reason that most front-end frameworks encourage users to manage state and component rendering in separate, loosely coupled modules.
