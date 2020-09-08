**If you have :**

- a decent knowledge of JavaScript but DON'T feel ready to start learning a front-end framework yet,
- been learning JS for while and you got tired/discouraged/bored or burnt out,
- been working on a beautiful JS project that makes you feel like it would be so cool to break your code in several parts/modules,

**this post might be for you!!!**
 
--------------------

By the quite emphatic title of this post, what i really mean is: 
as a JS learner, React **reactivated**💡 my drive/focus to keep learning and make progress with JavaScript + **boosted**🚀 my overall coding confidence. 
In a way, React saved my learning journey! I was feeling lost in a Javascript sea, somehow "tired" of vanilla JS...Hard to admit because i love JavaScript and i love writing code. That's why i do feel like React pretty much saved my life. Or at least my learning journey!

The plan of this article:
- [Why/How/when did i finally jump into React?](#1)
- [How much JavaScript did i know when i started with React (quite recently)](#2) 
- [React "philosophy": how steep is the learning curve exactly?](#3)
- [The HUGE Benefits of starting learning React](#4)
- [Are you ready to start? / You think you're not ready](#5)

<a name="1"></a>
## So here's how it all started.

*The trigger*

I was roaming the youtube streets in search of advice when i saw this comment under a great video on the topic of "from vanilla JS to a framework":

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/f7mp6uv29pyi72iknthr.png)

this is a short snippet of the comment this viewer wrote, but it's the part that struck me the most: he had put words onto this thing i had been feeling for a few weeks at this point. "nearly HATE JavaScript" may sound intense, but i could actually relate 100%! 
For me personnaly, just before meeting React in July, JavaScript had become difficult, somehow dry. Or maybe it was the learning journey itself (that was becoming difficult and dry)...
Anyways, this very comment sparked something in me: "oh cool i'm not alone!" and quickly: "i'm starting React tomorrow!"

<a name="2"></a>
**How much JavaScript did i know when i started with React:**
- general JS syntax (but still learning new things everyday lol)
- DOM manipulations and template literals, like:
```
const todayDiv = document.querySelector("#today");
const week = [tuesday, wednesday, friday, saturday, sunday];
const day = `<div class="whatever"> Hello! Today is ${week[0]}. Have a nice day!</div>`;
todayDiv.insertAdjacentHTML('afterbegin', day); 
```
- fetch data from an API + sense of what a promise is (#3LW for the connoisseurs😋) but without being able to explain it like a pro (unlike fetch()😎) but at least i knew fetch() is a promise (or rather, fetch() *returns* a promise, giving us access to methods like `.then()` or `.try()`/`.catch()` etc...) but i'll write/explain about `fetch` in another article soon!
- higher order functions (array methods like `forEach()` and `map()`, `filter()`, `sort()`, `push()` to add at the end of an array and `unshift()` to push at the beginning! 
*sidenote*: in a todo app for example, the `unshift()` method is very useful to make the dynamically added "todos" appear at the TOP of the list and not at the bottom... 😉 )
- basic knowledge of CLI (**C**ommand-**L**ine **I**nterface aka terminal).
- OOP basics (**O**bject **O**riented **P**rogramming) : it means i was able to create classes and use/understand the famous "this" keyword, without being utterly confused lol.
- basic knowledge of how JS works under the hood, which is very exciting to learn! (the callstack, lexical environment and scope, etc...)


**What was i scared of or impressed by:**
- the spread operator `...`: i had NEVER used it and had no idea what it was doing!
- destructuring `({ })` : more than scary, terrifying! still too abstract for me (that's what i thought) 
- using libraries (except for moment.js ❤️ ): i had never used bootstrap or any other library.
- React. plain and simple.  

*The encouragement*

On day I received a DM from my 100DaysOfCode friend Danny, who has experience as a developer, encouraging me to try implementing **with a framework** the vanilla JS todo-app i was working on! 
I could have chosen Vue.js as many people say Vue is the easiest front-end framework to learn, ideal for beginners! Which sounds great, but i thought "React!!!" because that's what i chose on the Roadmap of my coding journey and knowing i'll spend **time** learning a framework anyway (i follow the "learning by doing" method so it takes me some time to finish one project!) it'll be more time efficient for me to just jump into React.  
4 weeks later (it took me that long to feel "ready" to follow Danny's advice) i finally started to implement my todo app with React!🚀 
And here i am today, learning React, having a real blast at it, more excited than ever!

<a name="3"></a>
## React "philosophy" : steep learning curve?

React isn't that difficult for a JS beginner with some fundamental steady knowledge.
You just have to know 2 things:

**1- Think Component!**

No-brainer: a website or app is a construction **built** by different elements (navbar/menu, sections/pages, footer etc...). We agree on that.
So we can see these elements as the **components** of the website. 
That, in itself, is a MAJOR part of React.
In the code, you write the components as a class (class component) or a function (functional component). One js file for each component. No variable naming conflicts anymore and just perfect: components are reusable! of course! reusable in other projects (a contact form for example!), or in the same project several times (a button!)

So any component will be created like this:
- class component:
```
class MyComponent extends Component = {
  //some code
}
```
- or you can write it as a function (functional component):
```
function MyComponent(){
   //some code
}
```
- arrow function? yes:
```
const MyComponent = () => {
 // some code
}
```
OK. Look at the snippet below. This is the full code for an actual real component. Let's say the title of a website.
- class component:
```
class Title extends Component = {
 render(){
  return <h1> I am the f***ing Title component of the website!!! Sway!!! </h1>
 }
}
```
- same, functional component:
```
function Title(){
 return <h1> I am the f***ing Title component of the website!!! Sway!!! </h1>
}
```
- with arrow function:
```
const Title = () => {
 return <h1> I am the f***ing Title component of the website!!! Sway!!! </h1>
}
```
I know. Your brain is shouting: "HEY WAIT! isn't that HTML that i see in the return statement?"
Well, almost yes! It's... **JSX**!

**JSX, or: Forget about your index.html file!** 

To "create" the components we want, forget about the index.html file. React uses **JSX**. 
Though is sounds quite badass, it's just classic html "on steroids"!
On steroids or "enhanced" because you can write things like `<div> </div>` (many classic html tags are possible!!) but also `<MyComponent> </MyComponent>` or self-closing `<MyComponent />`. 

As you can see it's 100% html based and there is almost no learning curve there. I would even say that it's a great HTML refresher/booster!
So in other words: React "generates" the HTML of our project. "WAIT! REACT GENERATES THE HTML???" yes! you got it! Sorry if i spoiled the big reveal but that's an essential and exciting part of React. 
For the styling? classic CSS file. Or, to reduce the number of files and because it's super handy, it's also possible to write CSS in JS! There are many options to do that, but you'll discover them very soon! 

**2- The "state". What👏🏾 does👏🏾 it👏🏾 mean👏🏾 ?**
The other thing you will be doing all the time is managing state.
So what does it really mean? What is that "state" thing?
Let's start with: it's an object. 
```
state = {
 key:value,
 key:value
// etc...
}
```
The **state** is defined by YOU when creating your class component. It will **store** the data or starting point values used by the component that needs it.
(*sidenote*: the **state** is "initialized" in class components! 
It can also be handled by functional components, with the React HOOKS! I used to be so impressed by this word when in fact that's all it is: built-in React methods to manage state within functional components! But that's for another day 😉 ).

Back to our example, to create a classic Counter component, you would write:
 ```
 class Counter extends Component = {
  state = { count : 0 }
 }
 ```
This means that the starting point of our Counter is zero. 
Now: everytime the **state** of the Counter (count : 0) will be incremented or decremented, React will **render** or **re-render** (again and again) the Counter with its updated count on the screen. 
How does it work under the hood? Well, it's too complicated to explain right now and i'm not sure i could😋  but just to give you the main thing: React uses a virtual DOM... 

**Forget about DOM manipulations😈!** 

In React, you do NOT get to manipulate the DOM😈 !!! It's over. 
React "creates" the html we need and handles the DOM manipulations we want to achieve.
As we said earlier,  React **renders** the components (update of a timer or lazy-loading of a div for example) according to their **lifecycle**.

So how can we increment or decrement a counter if we can't manipulate the DOM ourselves? 
Well, it gets done with built-in React methods!😉 
The main one is: `setState()`. You will be using it all the time: `this.setState()`!
- in our Counter component it would look like:
```
 class Counter extends Component = {
  state = { count : 0 }
 
 incrementCounter = () => {
  this.setState({ count : this.state.count + 1 }) 
 }
} 
```

This is part of what's called **state management** (in a nutshell)! Not that crazy complicated, you see?

These 2 things, **Components** and **State** are at the core of what you may probably have heard people refer to as the *"React philosophy"*. 
Indeed, things are handled quite differently, but it's absolutely possible to start learning, even if you're not a JavaScript Jedi yet!


<a name="4"></a>
## The HUGE Benefits of starting to learn React now.

**Jump / Progress in JS knowledge**

- Because of React's class components, it will contribute to improve your OOP knowledge : you'll be writing a certain amount of  `this.state.myStuff`, `this.setState({ key : value })`, `this.state.otherStuff`, `this.myMethod`, `this.otherMethodOfMine`...
- faster then you know you will spend your time destructuring the state (it sounds so complicated now but trust me it is so simple once you are within React).
Also, you will have to use the spread operator `...`😬 all the time! Check this out: `[...array]` is the same as `array.slice()` and  `.slice()` is the array method to *make a copy* of an array. You'll need it a lot in React, to change/update a state! 
 
Today i'm so unimpressed by the spread operator and i'm destructuring the shht out of everything!😂 
And it's only been 2 weeks of learning sofar! You can do it too, for real.

**Get quicker to the goal of finding a junior dev job!**
Let's be honest: React is used by many companies. 
I think the sooner you jump into learning it, the better. You'll HAVE TO learn JavaScript either way! So why not do it with React? 2 stones 1 bird. But poor bird😢 so 1 stone 2 ricochets (or more than 2 actually😉 ) Awesome!

**Use of many great libraries, dependancies**
From *webpack* to bundle the project to *react-bootstrap* or *material-UI* for layout, *react-spring* for animations, *styled.components* or *emotion* to write CSS in JS a certain way (very cool!) and the list goes on!
This is how i quickly came to a real understanding of what it means to BUILD projects.


<a name="5"></a>
## You ARE ready to start! 👊🏾

Yeah, now is the moment when you drop everything you were doing and start learning React! 
You are in the middle of finishing yet another JS project? okay, keep at it BUT implement it with React!
1- open the terminal and type: ```npx install react```
2- create a folder for this very first react project!
3- back to terminal, make sure to locate yourself within this new folder (that is if you didn't create the folder from terminal using the ```mkdir``` command😉) and type: ```create-react-app``` (give a name to your project)
4- within your app folder on terminal, type:``` npm start```
BOOM the magic is starting!

Good luck on your journey!!! i'm still at it and having a lot of (productive) fun! 
All the best to you✊🏾 happy coding!

See you in the next article (i think it will be about promises).

