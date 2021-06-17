
# Browser JS

## Getting Started.

All other version of js (nodejs/coffescript ect..) compile to the same js standard which is described
by the w3c. documentation can be found on offical mozilla and w3c website.

https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics#language_basics_crash_course

As any interpreted language, it is read and executed at the same time.

### Variables

should be declared with `let` and initialize on the same line.

Good: `let myVar = "Hello World";` `let myVar = null;`
Bad: `let myVar;`

### Type

Object 	This can be anything. Everything in JavaScript is an object and can be stored in a variable.
Keep this in mind as you learn.

Other basic type exist (which are all objects) like string, number, array...

### Comparaison

Equality should always be done with `===`: This performs a test to see if two values are equal. It returns a true/false (Boolean)

### Condition

As all languages: `if (something) {} else if (something-else) {} else {}`

### Functions

use the keyword `function`
```js
function multiply(num1, num2) {
  let result = num1 * num2;
  return result;
}
```
## Deep into Frameworks

unless you have very few features to creates you will use a framework which today are really really
powerfull.

### React and Single Page Application

You’ll need to have Node >= 10.16 and npm >= 5.6

https://reactjs.org/docs/create-a-new-react-app.html#create-react-app

```bash
npx create-react-app my-app
cd my-app
npm start
```

npm start will start a temporary nodejs server to server your front.
It should open your default browser on `localhost:3000` and tell you: `Edit src/App.js and save to
reload.`
So let's do it ! (JUST DO IT !).

Change the `<p>..</p>` to `<h2> Hello World !</h2>`, save and VOILA !

Now we will never request a full html page again, only part of pages or some rest data using AJAX
query.

Here's the complete tutorial to start

https://www.taniarascia.com/getting-started-with-react/

### Compiling and deploying.

`npm run build`

A lot of tools exist, i will advice to stick to default react builder or to use webkit to start as it has a very large community.
