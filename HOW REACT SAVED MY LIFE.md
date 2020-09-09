**If you have :**

- a decent knowledge of JavaScript but DON'T feel ready to start learning a front-end framework yet,
- been learning JS for while and you got tired/discouraged/bored or burnt out,
- been working on a beautiful JS project that makes you feel like it would be so cool to break your code in several parts/modules,

**this post might be for you!!!**
 
--------------------

By the quite emphatic title of this post,

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/ab0bc6y5c2ijob868fmk.gif)

what i really mean is: 
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

this is a short snippet of the comment left by this person, but it's the part that struck me the most: he had put words onto this thing i had been feeling for a few weeks at this point. "nearly HATE JavaScript" may sound intense, but i could totally relate! 
For me personnaly, just before meeting React, JavaScript had become quite difficult, somehow dry. Or maybe it was the learning journey itself (that was becoming difficult and dry)...
Anyways, this very comment sparked something in me: "oh cool i'm not alone to feel that way!" and quickly: "i'm starting React tomorrow!"

<a name="2"></a>
**How much JavaScript did i know when i started with React:**

- general JS syntax (but still learning new things and tricks everyday lol)
- DOM manipulations and template literals, like:
```
const todayDiv = document.querySelector("#today");
const week = [tuesday, wednesday, friday, saturday, sunday];
const day = `<div class="whatever"> Hello! Today is ${week[0]}. Have a nice day!</div>`;
todayDiv.insertAdjacentHTML('afterbegin', day); 
```
- fetch data from an API + HTTP requests
- sense of what a promise is (#3LW for the connoisseurs😋) but without being able to explain it like a pro (unlike fetch()😎) but i knew fetch() is a promise (or rather, fetch() *returns* a promise, giving us access to methods like `.then()` or `.catch()`) but i'll write/explain about `fetch` in another article soon!
- array methods/higher order functions like `forEach()` and `map()`, `filter()` and the other array methods like `sort()`, `push()` to add at the end of an array and `unshift()` to push at the beginning! 
*sidenote*: when displaying a dynamic list for example, the `unshift()` method is very useful to make the dynamically added items appear at the TOP of the list and not at the bottom... 😉 )
- callbacks (in array methods/higher order functions for example)
- basic knowledge of CLI (**C**ommand-**L**ine **I**nterface aka terminal).
- OOP basics (**O**bject **O**riented **P**rogramming) : it means i was able to create classes and use/understand the "this" keyword, without being utterly confused lol.
- basic knowledge of how JS works under the hood, which is very exciting to learn! (the callstack, lexical environment, execution context etc...) - but you absolutely don't need to know that to start React. We have to know and understand how JS works under the hood in order to become better JS developers in general, not to learn React.

**What was i scared of or impressed by:**

- the spread operator `...`: i had NEVER used it and had no idea what it was for! I used ot find it very intimidating.
- destructuring `({ })` : scary because too abstract/complicated for me (that's what i thought) 
- writing promises other then fetch() in my code  
- writing `async` functions + use `await` keyword, i have to be honest here 😅
- using libraries (except for moment.js ❤️ ): i had never used bootstrap or any other library.
- React. plain and simple.  

*The encouragement*

On twitter, I received a DM from my 100DaysOfCode friend Danny, who has experience as a developer, encouraging me to try implementing **with a framework** the vanilla JS todo app i was working on! 
I could have chosen Vue.js as many people say Vue is the easiest front-end framework to learn, ideal for beginners! Which sounds great, but i thought "React!!!" because that's what i chose for the Roadmap of my coding journey and knowing i'll **spend time** learning a framework anyway (i follow the "learning by doing" method so it takes me some time to finish one project!) it'll be more time efficient for me to just jump into React.  
It took me some more time (3 weeks?) to feel "ready" to follow Danny's advice and i finally started to implement my todo app with React!🚀 
I actually had to rebuild it from the ground up! And it took me some time!
But here i am today, 100% learning React, todo app almost finished, having a real blast at it, more excited than ever to swim in JavaScript!

<a name="3"></a>
## React "philosophy" : steep learning curve?

React isn't that difficult for a JS beginner with some fundamental steady knowledge.
React offers a *different* approach for seeing and coding our websites. It's not as hard as you think. Trust me.
In fact, it's quite clever, powerful and fun!

This *different* approach is based on 2 main things:

**1- Think Component!**

No-brainer alert: a website or app is a construction **built** of different elements (navbar/menu, sections/pages, footer etc...). We agree on that.
So we can see these elements as the **components** of the website. 
Well that's React rule#1 in a nutshell!

In the code, you write the components as a class (class component) or a function (functional component). 1 (one) js file per component. No variable naming conflicts anymore and cherry on top: components are reusable! of course! reusable in other projects (a contact form for example!), or in the same project several times (a button!)

So any component will be created like this:
- class component:
```
class MyComponent extends Component = {
  //some code
}
```
- or you can write the same as a function (functional component):
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

OK. Look at the snippet below. This is the full code for an actual real component. 
Let's say the title component of a website.
- class component:
```
class Title extends Component = {
 render(){
  return <h1> I am the motherf*****g Title component of the website!!! Sway!!! </h1>
 }
}
```
- same component, functional:
```
function Title(){
 return <h1> I am the motherf*****g Title component of the website!!! Sway!!! </h1>
}
```
- arrow function, yes please:
```
const Title = () => {
 return <h1> I am the f***ing Title component of the website!!! Sway!!! </h1>
}
```
I know. Your brain is shouting: "HEY WAIT! isn't that HTML that i see in the return statement?"
Well, almost yes! It's in fact... **JSX**!

**JSX, or: Forget about your index.html file!** 

To "create" the components we want, forget about the traditional index.html file. React uses **JSX**. 
Though it sounds quite badass, it's just like classic html "on steroids".
It is actually JavaScript and NOT html, but as you can see the syntax looks 100% like html! That's why i would say that there's almost no learning curve there.
You can write things like `<div> </div>` (many classic html tags are possible!!) but also `<MyComponent> </MyComponent>` or self-closing `<MyComponent />`. 

So in other words: React "generates" the html of our project. "WAIT! REACT GENERATES THE HTML???" yes! you got it! Sorry if i spoiled the big reveal but that's an essential and exciting part of React. (Under the hood, React.createElement() does the magic ✨)
For the styling? classic CSS file. Or, to reduce the number of files and because it's super handy, it's also possible to write CSS in JS! There are many options to do that, but you'll discover them very soon! 

**2- The "state". What👏🏾 does👏🏾 it👏🏾 mean👏🏾 ?**

The other thing that's *different* is React handles our variables/data and the behaviour of our components!
Let me put it this way: **in React, our components will behave the way we want on screen based on their change of state**.
In other words, our components on screen are "reacting" to updates (or changes) of the variables/data they are responsible for.

In our code, the **state** is just an object:
```
state = {
 key:value,
 key:value
// etc...
}
```
The **state** is defined by YOU when creating your class component. It will **store** the data or starting point values used by the component that needs it.
(*sidenote*: the **state** is "initialized" in class components only! It can also be handled by functional components, with the React HOOKS! I used to be so impressed by this word when in fact that's all it is: built-in React methods to manage state within functional components! But that's another story you'll be knowing soon 😉 ).

So for example, to create a classic Counter component, you would write:
 ```
 class Counter extends Component = {
  state = { count : 0 }
 }
 ```
This means that the starting point of our Counter is zero. 
Now: everytime the **state** of the Counter (count : 0) will be incremented or decremented, React will **render** or **re-render** (again and again) the Counter with its updated count on the screen. 
How does it work under the hood? Well, it's too complicated to explain right now and i actually couldn't😋  but just to give you the main thing: React uses a virtual DOM and there's React.createElement()... 

**Forget about DOM manipulations😈 !** 

In React, you do NOT get to manipulate the DOM😈 !!! It's over. Under the hood: React.createElement(), remember?
React "creates" the html we need and handles the DOM manipulations we want to achieve.
As we said earlier,  React **renders** the components (update of a timer or lazy-loading of a div for example) according to their **state**.
This whole rendering thing corresponds to what's called the component's **lifecycle**. In React, we say that components are mounted or unmouted, some libraries use the terms "enter", "leaves" referring to the component! You see what i mean? 

So how can we increment or decrement a counter if we can't manipulate the DOM ourselves? 
Well, it gets done with built-in React methods!!😉  Let's not forget it's still all JavaScript, of course it comes with very cool and easy built-in methods!
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
Not that crazy complicated, you see? 

And now when you'll hear about **state management**, you'll know it's about handling the changes of **state** of a component. Or, the **sharing** of the state between several components! You'll be facing this situation very often and early on! 
And you will get it, i guarantee it.

These 2 things, **Components** and **State** are at the core of what you may probably have heard people refer to as the *"React philosophy"*. 
Indeed, things are handled quite **differently**, but it's absolutely possible to start learning, even if, like me, you're not a JavaScript Jedi yet!

<a name="4"></a>
## The HUGE Benefits of starting to learn React now.

**Jump / Progress in JS knowledge**

- Because of React's class components, it will contribute to improve your OOP knowledge : you'll be writing a certain amount of  `this.state.myStuff`, `this.setState({ key : value })`, `this.state.otherStuff`, `this.myMethod`, `this.otherMethodOfMine`...
- faster then you know you will spend your time destructuring the state (it sounds so complicated now but trust me it is so simple once you are within React).
Also, you will have to use the spread operator `...`😬 all the time! Check this out: `[...array]` is the same as `array.slice()` and  `.slice()` is the array method to *make a copy* of an array. You'll need it a lot in React, to change/update a state! You'll learn that **the state is immutable** (you canNOT change it dorectly like that), so you HAVE to make a *copy* of it (with the... spread operator 😋), update the copy as you want and paste the updated copy (like a copy/paste really!)
- Be sure of that: your JS knowledge with seriously incresase or strengthen by learning React!
 
Today i'm so unimpressed by the spread operator and i'm destructuring the shht out of everything!😂 
And it's only been 2 full weeks of learning sofar! You can do it too, for real. Just take your time, to each his/her own pace. 

**Get quicker to the goal of finding a junior dev job!**

Let's be honest: React is very popular on the job market. 
I think the sooner you jump into learning it, the better. You HAVE TO learn JavaScript either way! So why not do it with React? 2 stones 1 bird. But poor bird😢 so 1 stone 2 ricochets (or more than 2!😉 ) 

**Discovery of many great libraries, dependancies**

Also, React comes in with a plethora of tools, libraries, dependencies which is also very good for you to try, it will make you feel more at ease with *development*.  
From *webpack* to bundle the project to *react-bootstrap* or *material-UI* for layout, *react-spring* for animations, *styled.components* or *emotion* to write CSS- in-JS (very cool!) and the list goes on!
This is how i quickly came to a real understanding almost awakening of what it means to BUILD projects.

<a name="5"></a>
## You ARE ready to start! 👊🏾

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/ys2819ozquqv37o84ocp.gif)

Yeah, now is the moment when you drop everything you were doing and start learning React! 
You are in the middle of finishing yet another JS project? okay, keep at it BUT implement it with React!
1- open the terminal and type: `npx install react`
2- create a folder for this very first react project!
3- back to terminal, make sure to locate yourself within this new folder (that is if you didn't create the folder from terminal using the `mkdir` command😉) and type: `create-react-app` (give a name to your project)
4- within your app folder on terminal, type:`npm start`
BOOM the magic is starting!


Good luck on your journey!!! i'm still at it and having a lot of (productive) fun! 
All the best to you✊🏾 happy coding!

See you in the next article (i think it will be about promises).

