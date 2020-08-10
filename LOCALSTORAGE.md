# THE "LOCAL STORAGE"

### You need some dynamically created data to remain on screen AFTER the user hits the browser refresh button?
### You need to SAVE the user's input.value somewhere? (because you just need to.)
### Well, good news: that's what the localStorage is here for!!!🤩 


**If you need to:**
- save the value of some sort of counter and not have it reset to 0 each time you refresh the page
- save the user's input.value somewhere? (because you just need to)
- keep dynamically created data on the screen AFTER a browser refresh
- or anything like that

**Well, good news: that's what `localStorage` is here for!!!🤩**
 
--------------------

**Let's dive into it**

The project case i'll use here is a good old to-do list, as it is exactly the kind of situation where we would really need to use localStorage.
In a todo app, the user types something he wants to add to the list (in the input field) and when he presses the "add" or "submit" button, it gets added to the screen. 
To achieve that, we do a DOM manipulation, using one of the following methods: 
- [`createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement) + [`appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild) 
- or the one dear to my heart: [`insertAdjacentHTML()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML). 

*You can click on each of them to see more information, in case you are not familiar with those DOM manipulation methods yet.*

So, our todo app could be looking like this (or way simpler or better of course):


Great!

But there's a **problem**: everytime we refresh the page, it all goes away... There's absolutely no onscreen persistence of the items we add, **once we hit the refresh button of our browser, our list goes empty**.🔄 😭

That's precisely when `localStorage` comes into play!
The Local Storage is a sort of browser database, that can save our data as strings (key/value pair objects).
You can see the Local Storage in the devtools: instead of "console"😉, go to "application" (you might need to click on the little double-arrow on the right to have access to it). 
Here it is:

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/kq4o40maxhp5kweut6mj.png)

This is where we can store our data!!


**Here's how.**

To create your storage :
`localStorage.setItem("mySuperStorage","yay!")`
If you type that in your console right now, on the google homepage for example, no problem, you'll see the following🤩: 

IMAGE SPLIT CONSOLE + STORAGE

As simple as that.

To retrieve the data that you stored there:
`localStorage.getItem("mySuperStorage")`

IMAGE IN THE CONSOLE

**Okay, and how does this work really?**

Under the hood:
- localStorage is a property of the Window object. 
- it stores data permanently (unless you erase it, we'll see how),
- there is one localStorage per website/domain,
- which means that it doesn't matter if you have multiple tabs of the same website opened, it's the same localStorage as long as you are on this website (which is great!).
- maximum size is about 5mb (which is plenty for storing key/value pairs. Those are just strings!)

From a code perspective, localStorage comes in with 5 built-in methods.
The ones we'll use all the time:
- `localStorage.setItem(name, content)`: setItem() lets you create your storage(s). The 1st parameter is the name you want to give to your storage, the 2nd parameter is what you want to put in this storage. You can create as much storages as you want!
- `localStorage.getItem(name)`: getItem() lets you retrieve the data you stored in the storage. You have to specify the name of the data you want (name that you decided).
- `localStorage.clear()`: the `clear()` method erases everything from the storage. No parameter needed, quick and easy!

And also:
- `localStorage.remove(key)`: to remove/erase the corresponding value of the key you specified (if your storage name is "abc": `localStorage.remove("abc")` will remove/erase your storage). 

- `localStorage.key(number)`: here the number parameter works like the index for an array. So this method will give you the key or the name it will find at that "index" of the localStorage. It will work if you have several items or storages within localStorage.

IMAGE CONSOLE

**Now let's implement it in our TODO app example!** 
We'll want to:
1- [create a storage with localStorage.setItem()](#1)
2- [store each new task added by the user, in that storage!](#2) 
3- [display all the todos stored in the localStorage after the user refreshes the browser or even closes the window and comes back!](#3)

<a name="1">1- Let's create a storage with localStorage.setItem()</a>
```
const todoStorage = [];  
localStorage.setItem("TODO-app storage", JSON.stringify(todoStorage)); 
```
- 1st line of code:
`const todoStorage = []`: this creates an empty array (which will store all the todos entered by the user.
- now let's break the 2nd line of code in 2 parts:
 - `localStorage.setItem("TODO-app storage",`: this piece creates a storage named "TODO-app Storage" in our localStorage. 
 - `JSON.stringify(todoStorage)`: this piece will turn the data we put in the storage into strings.
Let's not forget that everything is a string in localStorage BUT in our JavaScript code, under the hood, our data is actually in JSON format (JavaScript Object Notation). So it HAS to be turned into strings in order to be stored in localStorage. 
To do that, thankfully we have the built-in `JSON.stringify()`  method!
Now is the moment you might ask: "okay so to retrieve the data from localStorage we will have to do the opposite, right? turn the strings back into JSON format?" and yes absolutely!!!🤩
It gets done using the `JSON.parse()` method.
We'll use it shortly. 

At this point, if we check our localStorage, we see this:

IMAGE LOCAL STORAGE

<a name="2">2- Let's store each new task added by the user, in the storage! </a>
1- `const todo = { task: input.value };` : this is what the user types in the input and submits to the screen. we declare a "todo" variable to be an object with a property we decided to call "task", which stores the value (the text) that gets typed in the input by the user. 
2- `todoStorage.push(todo);` : easy array method to add the todo to the array todoStorage, the empty one we created earlier. 
3- `localStorage.setItem("TODO-app storage", JSON.stringify(todoStorage));` : now we set the Local Storage content to be that of our array todoStorage!
let's wrap all that in a function that we could call storeTodos():
```
function storeTodos(){
const todo  = {task: input.value};
todoStorage.push(todo);
localStorage.setItem("TODO-app storage",JSON.stringify('todoStorage'));
}
```
or 
```
const storeTodos = () => {
const todo  = {task: input.value};
todoStorage.push(todo);
localStorage.setItem("TODO-app storage",JSON.stringify('todoStorage'));
}
```

Let's invoke that function when the submit button is clicked for example!
We should see our localStorage in action!

IMAGE

<a name="3">3- Let's display all the todos stored in the localStorage after the user refreshes the browser or even closes the window and comes back!</a>

We'll manage to do that thanks to 2 things:
1- a function to display the todos
```
function displayTodos() {
 const todoStorage = JSON.parse(localStorage.getItem('todoStorage')) || [];
 todoStorage.forEach((todo) => {
    const userItem = `<li class="my-css">
                      <i class="far fa-square"></i>                     
                      <p class="my-css">${todo.task}</p>
                      <i class="far fa-trash-alt"></i>
                     </li>`;
    document.querySelector(".todo-list").insertAdjacentHTML("beforeend", userItem);
  }
}
```
2- an event listener on the window to know when the page gets refreshed (or closed and reopened). We'll invoke the displayTodos function at that moment!
```
window.addEventListener('DOMContentLoaded', displayTodos);
```
and that's a wrap!!

let's break that down:
DOMContentLoaded event:


That was it about the Local Storage! 
I hope this article will help or give you some inspiration for your own projects.

Next article next week!🤙🏾



 


  


