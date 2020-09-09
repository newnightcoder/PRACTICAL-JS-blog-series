**If you are :**

- having doubts about your coding "level" to start learning React,
- at a decent "level" of knowledge of JavaScript but don't feel ready to start learning a front-end framework yet,
- learning JS and got tired/discouraged/bored or burnt out,
- working on a beautiful front-end project that makes you feel like 1000+ lines of codes are a bit much all in ONE JS file,
- in need of some novelty/excitement/challenge/motivation in your coding journey,
- thinking React is NOT for you cause it's too difficult,

**this post might be for you!!!**
 
--------------------

By the quite dramatic title of this post,

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/ab0bc6y5c2ijob868fmk.gif)

what i really mean is: 
as a JS learner, React **reactivated**💡 my drive/focus to keep learning and make progress with JavaScript + **boosted**🚀 my overall coding confidence. 
I was feeling lost in a Javascript sea, somehow "tired" of vanilla JS...Hard to admit, because i love JS and i love writing code. That's why i do feel like React pretty much saved my life. Or at least my learning journey!

The plan of this article:
- [Why/How did i finally jump into React?](#1)
- [How much JavaScript did i know when i started with React recently?](#2) 
- [React "philosophy": how steep is the learning curve exactly?](#3)
- [The HUGE Benefits of starting learning React](#4)
- [Are you ready to start? / You think you're not ready](#5)

<a name="1"></a>
## So here's how it all started.

*The trigger*

I was roaming the youtube streets in search of advice/inspiration when i saw this comment:

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/f7mp6uv29pyi72iknthr.png)

This is a short snippet of what this viewer wrote, but it's the part that struck me the most: he had put words onto this thing i had been feeling for a few weeks at this point. "nearly HATE JavaScript" may sound intense, but i could totally relate! 
For me personally, just before meeting React, JavaScript had become quite difficult, somehow dry. Or maybe it was the learning journey itself (that was becoming difficult and dry)...
Anyways, this very comment sparked something in me: "oh cool i'm not alone to feel that way!" and quickly: "i'm starting React tomorrow!"

*The extra push*

Shortly after that, I received a DM on twitter from my 100DaysOfCode friend Danny (who has experience as a developer) encouraging me to try implementing **with a framework** the vanilla JS todo app i was working on! 
I could have chosen Vue.js as many people say Vue is the easiest front-end framework to learn, ideal for beginners! Which sounds great, but i thought "React!!!" because that's what i chose for the Roadmap of my coding journey and knowing i'll **spend time** learning a framework anyway (i follow the "learning by doing" method so it takes me some time to finish one project!) it'll be more time efficient for me to just jump into React.  
It took me some more time (3 weeks?) to feel "ready" to follow Danny's advice and i finally started to implement my todo app with React!🚀 
I actually had to rebuild it from the ground up! 
But here i am today, 100% learning React, todo app almost ready, having a real blast at it, more excited than ever to swim in JavaScript!

<a name="2"></a>

## How much JS did i know when i started with React:

- general JS syntax (but still learning new things and tricks almost everyday lol)
- DOM manipulations and template literals, like:
```javascript
const todayDiv = document.querySelector("#today");
const week = [tuesday, wednesday, friday, saturday, sunday];
const day = `<div class="tuesday"> Hello! Today is ${week[0]}. Have a nice day!</div>`;
todayDiv.insertAdjacentHTML('afterbegin', day); 
```javascript
- fetch data from an API + HTTP requests
- sense of what a promise is (#3LW for the connoisseurs😋) but without being able to explain it like a pro (unlike fetch()😎) but i knew fetch() is a promise (or rather, fetch() *returns* a promise, giving us access to methods like `.then()` or `.catch()`) but i'll write/explain about `fetch` in another article soon!
- array methods/higher order functions like `forEach()` and `map()`, `filter()` and the other array methods like `sort()`, `push()` to add at the end of an array and `unshift()` to push at the beginning! (*sidenote*: when displaying a dynamic list for example, the `unshift()` method is very useful to make the dynamically added items appear at the TOP of the list and not at the bottom... 😉 )
- callbacks (in array methods/higher order functions for example)
- basic knowledge of CLI (**C**ommand-**L**ine **I**nterface aka terminal)
- OOP basics (**O**bject **O**riented **P**rogramming) : it means i was able to create classes and use/understand the "this" keyword, without being utterly confused lol
- basic knowledge of how JS works under the hood, which is very exciting to learn! (the callstack, lexical environment, execution context etc...) - but you absolutely don't need to know that to start React. We have to know and understand how JS works under the hood in order to become better JS developers in general, not to learn React.

**What was i scared of or impressed by:**

- the spread operator `...`: i had NEVER used it and had no idea what it was for! I used to find it very intimidating
- destructuring: scary because too abstract/complicated for me (that's what i thought) 
- writing promises other then fetch() in my code  
- writing `async` functions + use `await` keyword, i have to be honest here 😅
- using libraries (except for moment.js ❤️ ): i had never used bootstrap or any other library
- React. plain and simple.  


<a name="3"></a>

## React "philosophy" : steep learning curve?

React isn't that difficult for a JS beginner with some "basic" but steady knowledge.
React offers a *different* approach for seeing and coding our websites. It's not as hard as you think. Trust me.
In fact, it's quite clever, powerful and fun!

This *different* approach is based on 2 main things:

**1- Think Component!**

No-brainer alert: a website or app is a construction **built** of different elements (navbar/menu, sections/pages, footer etc...). We agree on that.
So we can see these elements as the **components** of the website. 
Well, that's React rule#1 in a nutshell!

In the code, you write the components as a class (class component) or a function (functional component). 1 (one) JS file per component. No variable naming conflicts anymore and cherry on top: components are reusable! of course! reusable in other projects (a contact form for example!), or in the same project several times (a button!)

So any component will be created like this:
- class component:
```javascript
class MyComponent extends Component = {
  //some code
}
```
*by the way:* the `Component` class that we extend to create our components comes from React!😉
We import it at the very top of the file.
- you can write the same as a function (functional component):
```javascript
function MyComponent(){
   //some code
}
```
- arrow function? yes:
```javascript
const MyComponent = () => {
 // some code
}
```

OK. Look at the snippet below. This is the full code for an actual real component. 
Let's say the title component of a website.
- class component:
```javascript
class Title extends Component = {
 render(){
  return <h1> I am the motherf*****g Title component of the website!!! Sway!!! </h1>
 }
}
```
- same component, functional:
```javascript
function Title(){
 return <h1> I am the motherf*****g Title component of the website!!! Sway!!! </h1>
}
```
- arrow function, yes please:
```javascript
const Title = () => {
 return <h1> I am the motherf***ing Title component of the website!!! Sway!!! </h1>
}
```
I know. Your brain is shouting: "HEY WAIT! isn't that HTML that i see in the return statement?"
Well, no. It's... **JSX**!
And have you noticed the `render()`method in the class component? It belongs to the Component class of React and is responsible for displaying, **rendering** the JSX! As you can see, functional components have no `render()`, which makes sense: they're not classes! They just use the `return` statement.

**JSX, or: Forget about your index.html file!** 

To create the components we want, forget about the traditional index.html file. React uses **JSX**. 
You could see JSX as "JS disguised as html-on-steroids".
So JSX is actual JavaScript that looks 100% like html! 
That's why i would say that there's almost no learning curve there.
You can write things like `<div> </div>` (many classic html tags are possible!!) but also `<MyComponent> </MyComponent>` or self-closing `<MyComponent />`. 

So in other words: React "generates" the html of our project. I know. "WAIT! WHAT? REACT GENERATES THE HTML???" yes! you got it! Sorry if i spoiled the big reveal but that's an essential and exciting part of React. 
For the styling? classic CSS file. Or, to reduce the number of files and because it's super handy, it's also possible to write CSS in JS! There are many options to do that, but you'll discover them very soon! 

**2- The "state". What👏🏾 does👏🏾 it👏🏾 mean👏🏾 ?**

The other thing that's *different* is the way React handles our variables/data and the behaviour of our components!
Let me put it this way: **in React, our components will behave on screen the way we want them to, based on their change of state**.
In other words, our components on screen are "reacting" to updates (or changes) of the variables/data they are responsible for, their **state**.

In our code, the **state** is simply an object!
```javascript
state = {
 key:value,
 key:value
// etc...
}
```
The **state** is defined by YOU when creating your class component. It will **store the data** or **starting point value** used by the component that needs it.
(*sidenote*: the **state** is "initialised" in class components only! It can also be handled by functional components, with the React HOOKS! I used to be so impressed by this word when in fact that's all it is: built-in React methods to manage state within functional components! But that's another story you'll be reading soon 😉 ).

So for example, to create a classic Counter component, you would write:
 ```javascript
 class Counter extends Component = {
  state = { count : 0 }

  render(){
   return <div> {this.state.count} </div>
  }
 }
 ```
This means that the starting point of our Counter is zero. 
Now: everytime the **state** of the Counter (count : 0) will be incremented or decremented, React will **render** or **re-render** (again and again) the Counter with its updated count on the screen. 
How does it work under the hood? Well, it's too complicated to explain right now and i actually couldn't😋  but just to give you the main thing: React uses a virtual DOM and there's React.createElement()... 

**Forget about DOM manipulations😈 !** 

In React, you do NOT get to manipulate the DOM😈 !!! It's over.😭 But wait! React is awesome, trust me on this one.
React "creates" the html we need and handles the DOM manipulations we want to achieve.
Under the hood: React.createElement(), remember?
As we said earlier,  React **renders** (or **re-renders**) the components according to their **state** (update of a timer or dark-mode toggle for example).
This whole rendering thing corresponds to what's called the component's **lifecycle**. In React, we say that we "mount"/"unmount" components, or components are "mounted"/"unmounted", various libraries use terms like "enter", "active", "exit" referring to the component! You see what i mean? 

So how can we increment or decrement a counter if we can't manipulate the DOM ourselves? 
Well, it gets done with built-in React methods!!😉  Let's not forget it's all JavaScript, so of course it comes with very cool and easy to use built-in methods!
The main one is: `setState()`. You will be using it all the time! `this.setState()`
- in our Counter component, it would look like:
```javascript
 class Counter extends Component = {
  state = { count : 0 }
 
  incrementCounter = () => {
   this.setState({ count : this.state.count + 1 }) 
  }

  render(){
   return( 
    <div>
     <button onClick = {this.incrementCounter}> Click me to increment the counter below! <button>
     <div>{this.state.count}<div/>
    </div>
   )
  }
 } 
```
Not that crazy complicated, you see? 
And this counter works perfectly! You press the button and the number in the div just below increases! (you need to add some css of course😋 but you know how to do that!)
I know you still might have some reservations but i'm sure you understand this simple counter by just reading the code. Self-explanatory enough, right?
Everytime we press the button, it **changes** the **state** of our Counter **component** (in this example we increment it) , so React **re-renders** our updated Counter each time we click the button!🤩

So now when you'll hear about **state management**, you'll know it's about handling the changes of **state** of a component. Or, the **sharing** of the state between several components! You'll be facing this situation very often and early on! 
And you will get it, i guarantee it.

These 2 things, **Components** and **State** are at the core of what you probably have heard people refer to as the *"React philosophy"*. 
Indeed, things are handled quite *differently*, but it's absolutely possible to start learning it now, even if like me, you're not a JS Jedi yet!😅

<a name="4"></a>

## The HUGE Benefits of starting to learn React now.

**Jump / Progress in JS knowledge**

- Because of React's class components, you will improve your OOP practice : you'll be writing a certain amount of  `this.state.myStuff`, `this.setState({ key : value })`, `this.state.otherStuff`, `this.myMethod`, `this.otherMethodOfMine`...
- Faster than you know, you'll spend your time destructuring the state (it sounds so complicated now but trust me it is so simple once you are within React).
Also, you will have to use the spread operator `...`😬 all the time! Check this out: `[...array]` is the same as `array.slice()`. And  `.slice()` is the array method to *make a copy* of an array. You'll need it a lot in React, to change/update the state! Indeed, you'll learn that **the state is immutable** and it has consequences. But don't panic, React has several major built-in methods to deal with that.
- You can be 100% confident that your JS knowledge will seriously rocket or at least strengthen, by learning React!
 
Today i'm so unimpressed by the spread operator and i'm destructuring the shht out of everything!😂 
And it's only been 2 full weeks of learning sofar! You can do it too, for real. Just take your time, to each his/her own pace. 

**Get quicker to the goal of finding a junior dev job!**

Let's be honest: React is very popular on the job market. 
I think the sooner you jump into it, the better. You HAVE TO learn JavaScript  anyway! So why not do it with React? 1 stone 2 birds. But poor birds😢 so 1 stone 2 skips!! (much more than 2..😉 ) 

**Discovery of many great libraries, dependencies**

React comes in with a plethora of available tools, libraries, dependencies, which are also very good for you to try. It will make you feel more at ease with web *development* in general.  
From *webpack* to bundle the project to *react-bootstrap* or *material-UI* for layout, *react-spring* for animations, *styled.components* or *emotion* to write CSS- in-JS (very cool!) and the list goes on!
This is how i quickly came to a real understanding - almost awakening - of what it really means to BUILD projects. This is all architecture! How great!!!
Of course that's not all there is behind the concept of "building" a project but we're getting there!

<a name="5"></a>

## You ARE ready to start! 👊🏾

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/ys2819ozquqv37o84ocp.gif)

Yeah, now is the moment when you drop everything you were doing and start learning React! 

1- create a folder for your very first React project! yes let's do it!
2- open the terminal (make sure to locate yourself within this new folder you just created) and type: `npx create-react-app my-app`
3- once the installation is complete in the terminal, you can read: 
```
 cd my-app
 npm start

Happy hacking!
```
3- so, type as they say: `cd my app` and hit enter😉
4- now type: `npm start`, hit enter, wait a moment, wait...
AND BOOM!🚀 the magic is starting!
Welcome to React my fellow learner!

Good luck on your journey!!! i'm still at it and having a lot of fun! Let's keep learning!✊🏾
All the best, and thank you for reading!

See you in the next article (shorter i **promise**😋).

