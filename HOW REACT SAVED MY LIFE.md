**If you have :  in one of these situations:**

- a decent knowledge of JavaScript but DON'T feel ready to start learning a front-end framework yet,
- been learning JS for while and you got tired/discouraged/bored or burnt out,
- been working on a beautiful JS project that makes you feel like it would be so cool to break your code in several parts/modules,

**this post might be a good read for you!!!**
 
--------------------

By the quite emphatic title of this post, what i really mean is: 
as a JS learner, React **reactivated**💡 my drive/focus to keep learning and make progress with JavaScript + **boosted**🚀 my overall coding confidence. 
In a way, React saved my learning journey! I was feeling lost in a Javascript sea, somehow "tired" of vanilla JS...Hard to admit because i love JavaScript and i love writing code. That's why i do feel like React pretty much saved my life.

The plan of this article:
- [Where was i in terms of learning when i started with React (quite recently)](#1) 
- [Where or what is the learning curve exactly? / 2 things you'll have to know.](#2)
- [The HUGE Benefits of starting learning React](#3)
- [Are you ready to start? / You think you're not ready](#4)


## 1- So here's how it all started.

*The trigger*

I was roaming the youtube streets in search of advice when i saw this comment under a great video on the topic of "from vanilla JS to a framework":

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/f7mp6uv29pyi72iknthr.png)

this is a short snippet of the comment this viewer wrote, but it's the part that stuck to me the most. he had put words onto this thing i had been feeling for a few weeks at this point. "hate" may be a strong word, but i could relate so much! then the viewer explains his journey and it's very interesting. for me personnaly, JavaScript had become difficult, somewhat dry. Or maybe it was the learning journey itself (that was becoming difficult and dry)...
anyways, this very comment sparkled something in me, "i'm not alone!" and quickly: "i'll start react tomorrow!"

<a name="1"></a>
**What did i know, code-wise:**
- general JS syntax (but still learning new things everyday lol)
- dom manipulation 
- fetch from an API + sense of what a promise is (#3LW for the connoisseurs lol) but without being able to explain it like a pro, unlike fetch()😎lol, but i knew fetch() is a promise. i'll write/explain about ```fetch```in another article.
- higher order functions (array methods)
- basic knowledge of cli (**c**ommand-**l**ine **i**nterface aka terminal).
- OOP basics (**o**bject **o**riented **p**rogramming) : it means i was able to create classes and use/understand the famous "this" keyword, as long as it was not too tricky. 

**What was i scared of or impressed by:**
- the spread operator 
- destructuring
- using libraries (except for moment.js ❤️). i had never tried bootstrap or anything like that.
- React. plain and simple. 

*The switch moment*
i received a dm from a nice 100DaysOfCode friend of mine, Danny, encouraging me to implement the vanilla JS todo-app i was working on, with a framework. I could have chosen Vue, many people say Vue is the easiest front-end framwork to learn, great for beginners! Which is great, but i thought "React!!!" because that's what i chose for my learning roadmap and i thought: i'll spend **time** learning a framework anyway (i follow the "learning by doing" method so it still takes me some time to finish one project! lol) so it'll be more time efficient if i start with React NOW.  
I finally started to implement my todo app with React (took me about 3 weeks after the dm of my friend to feel "ready" lol)
And here i am today, learning React and having a real blast!

<a name="2"></a>
## React "philosophy"
React isn't this difficult as a beginner.
You just have to know or *realize* 2 things:
**1- Think Component!**

No-brainer: a website or app is **built** by different elements (navbar/menu, sections/pages, footer etc...). We agree on that.
So it means that these elements are the **components** of the website. 
That only is a MAJOR part of React (and i guess of the other 2 front-end framworks Vue and Angular, but not sure as i have not yet worked with them).
In the code, you write the components as classes (class component) or functions (functional components).
So any component will start like this:
class component:
```
class MyComponent extends React.Component = {
  //some code
}
```
the same, functional component:
```
function MyComponent(){
   //some code
}
```
You prefer arrow functions? okay:
```
const MyComponent = () => {
 // some code
}
```
**JSX, or: Forget about the index.html file.**
Now. Look at this. This is the code for an actual real component. Let's say the title of a website.
Full code, class component:
```
class Title extends React.Component = {
 render(){
  return <h1> I am the f***ing Title component of this website!!! How sway!!! </h1>
 }
}
```
same, functional component (arrow functions are always possible as well of course):
```
function Title(){
 return <h1> I am the f***ing Title component of this website!!! How sway!!! </h1>
}
```
I know. Your brain is shouting to you: "HEY WAIT! is that HTML that i see in the return statement?"
Well, almost... It's **JSX**. 
To "create" the components we want, forget about the index.html file. React uses **JSX**. 
Though is sounds quite badass, it's just classic html "on steroids"!
On steroids or "enhanced" because you can write things like ```<div> </div>``` (use of many classic html tags is possible!!) but also ```<MyComponent> < /MyComponent>``` or self-closing ```<MyComponent />```. 
As you can see it's 100% html based and there is no learning curve there. I would even say that it's a great html refresher/knowledge enhancer!
In other words: *React generates the html* "WAIT! REACT GENERATES THE HTML???" yes! you got it! That's a very exciting part of React. Sorry if i spoiled the big reveal but that's essential to feel comfortable with React. That's what you'll be doing all the time.
For the styling? classic CSS file. Or, to reduce filesize and because it's super handy, it's also possible to write CSS in JS! There are many options to do that, but you'll discover them very soon! 

**Forget about DOM manipulations😈**
React does them for us. React creates the html we need and handles the DOM manipulations we want to achieve.
Because of that, we say that React **renders** a component or **re-renders** it if there is a DOM manipulation to do (update of a timer or lazy-loading of a div for example).



**2- The "state". What👏🏾does👏🏾 it👏🏾 mean👏🏾 ?**
The other thing you might be doing all the time is managng state.
So what does it really mean? What is that "state" thing?
Well, it's an object: 
```
state = {
 key:value,
 key:value
// etc...
}
```
That was for a functional component. 
Of course, in a class component it would be written:
```
this.state = { 
 key:value
 key:value
 etc...
}
```
The state is defined by YOU when creating your component. It will **store** the data or starting point values used by the component that needs it.
For example, to create a classic Counter component, you have to do like this:
OOP (class): ```this.state = { counter : 0 }``` or FP (function): ```state = { counter : 0 } ```  

This means that the starting point of your counter is zero. With built-in React functions/methods, you'll be able to increment/decrement the Counter component on screen. This is called **state management**! Not that complicated, you see?
Note that you will achieve this kind of things without EVER having to code for any DOM manipulation: in React, you do NOT get to manipulate the DOM😈 !!! React does it for us. 
Everytime the state of the Counter is updated, React **re-renders** the updated component on the screen. Or the component is re-rendered.
How does it work under the hood? Well, it's too complicated to explain now and i'm not sure i could😋  but just to give a hint: React uses a virtual DOM. 
You DO NOT manipulate the DOM. You have to forget about this way of doing things.

These 2 things, **Components** and **State** are at the core of what you may problably have heard people refer to as the *"React philosophy"*. 
So, things are handled very differently, indeed, but it's absolutely possible to start learning, even if you're not a JavaScript Jedi yet!


<a name="3"></a>
## The HUGE Benefits of starting to learn React now.
**Jump / Progress in JS knowledge**
 - Your OOP knowledge, ease will increase dramatically!! : you'll be writing an insane amount of ```this.state.myStuff```, ```this.state.otherThing``` or ```this.myMethod```, ```this.otherMethodOfMine```.
You'll use the "this" keyword a lot (in class components) and get a good grasp/understanding of OOP style.

- faster then you know you will spend your time destructuring the state (it sounds so complicated now but trust me it is simple once you are within React).
Also, you will have to use the spread operator😬 a lot! What i wish i'd known earlier on: this: ```[...array]``` is the same as ```array.slice()``` and  ```.slice()``` is the array method to *make a copy* of an array. You'll need it a lot in React, for your state management! all the time! 
Today i'm so unimpressed by the spread operator now and i'm destructuring the sht out of everything! And it's only been 3 weeks or so since i started!
**Quicker to the goal of being employable one day**
**Use of many great libraries, dependancies**
**Get to use webpack for real!**

<a name="4"></a>
## Words of encouragement 👊🏾

So, yeah, now is the moment when you drop everything you were doing and start learning React! 
But you are in the middle of finishing yet ANOTHER js project? okay, keep at it BUT implement it with React!
1- open the terminal and type: ```npx install react```
2- create a folder for this very first react project!
3- back to terminal, make sure to locate yourself within this new folder (that is if you didn't create the folder from terminal using the ```mkdir``` command😉) and type: ```create-react-app``` (give a name to your project)
4- within your app folder on terminal, type:``` npm start```
BOOM the magic is starting!

Good luck on your journey!!! i'm still at it and having a lot of (productive) fun! 
All the best to you✊🏾 happy coding!

See you in the next article (i think it will be about promises).

