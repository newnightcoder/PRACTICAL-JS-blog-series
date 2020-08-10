# THE "LOCAL STORAGE"


**If you need to:**
- save the value of some sort of counter and not have it reset to 0 each time you refresh the page
- save the user's input.value somewhere (because you need to)
- keep dynamically created data on the screen AFTER a browser refresh
- or anything like that

**Well, good news: that's what `localStorage` is here for!!!🤩**
 
--------------------

### Let's dive into it

The project i'll be using as an example here is my TO-DO list, as it is exactly the kind of situation where we would really need to use localStorage.
In a TO-DO app, the user types something he wants to add to the list (in the input field) and when he presses the "add" or "submit" button, it gets added to the screen. 

To achieve that, we "manipulate" the DOM 😈, using one of the following methods: 
- [`createElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement) + [`appendChild()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild) 
- or the one dear to my heart: [`insertAdjacentHTML()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/insertAdjacentHTML). 

*You can click on each of them to see more information, in case you are not yet familiar with DOM manipulation.*


![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/sm5oybd1accwszl7nx1g.gif)
Cool!

But there's a **problem**: everytime we refresh the page, it all goes away... There's no onscreen persistence of the items we add. 
**Once we hit the refresh button of our browser, our list goes empty**.🔄 😭 We need to fix this!

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/alexnid60865qmgiurxy.gif)

That's precisely when `localStorage` comes into play!
The Local Storage is a sort of browser database, that can save our data as strings (key/value pair objects).
You can see the Local Storage in the devtools: instead of "console"😉, go to "application" (you might need to click on the little double-arrow on the right to have access to it). 
Here it is:

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/kq4o40maxhp5kweut6mj.png)

This is where we can store our data!!


### Here's how.

**To create a storage:**
`localStorage.setItem("mySuperStorage","yay!")`
If you open a new tab in your browser, type that code in your console (+ press enter), you'll see the following🤩: 

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/biyibbakx2z5zbd2jhdt.png)

As simple as that.

**To retrieve the data we stored:**
`localStorage.getItem("mySuperStorage")`

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/jrs7cf5xqtd7829hxb8c.png)

### Okay, and how does this work really?

**Under the hood**:
- localStorage is a property of the Window object
- it stores data permanently (unless you erase it, we'll see how below)
- there is one localStorage per website/domain
- which means that it doesn't matter if you have multiple tabs of the same website opened, it's the same localStorage as long as you are on this website (which is great!)
- maximum size is about 5mb (which is plenty for storing key/value pairs. They are just strings, very light!)

**In our code**, localStorage comes in with 5 built-in methods.
The ones we'll use all the time are:
- `localStorage.setItem(name, content)`: setItem() lets you create your storage(s). The 1st parameter is the name you want to give to your storage, the 2nd parameter is what you want to put in this storage. You can create as many storages as you want!
- `localStorage.getItem(name)`: getItem() lets you retrieve the data you stored in the storage. You have to specify the name of the data you want (= the name that you gave to your storage).
- `localStorage.clear()`: the `clear()` method erases everything from the storage. No parameter needed, quick and easy!


### Now let's implement it in our TODO app example!
We're going to:
- [create a storage with localStorage.setItem()](#1)
- [store each new task added by the user, in that storage!](#2) 
- [display all the todos stored in the storage after the user refreshes the browser or closes the window and comes back!](#3)

For now, our localStorage is empty. It hasn't been initialized yet.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/9jahautzccy6f0w1ul8n.png)

**<a name="1">1- Let's create a storage with localStorage.setItem()</a>**

```
const todoStorage = [];  
localStorage.setItem("TODO-app storage", JSON.stringify(todoStorage)); 
```
- 1st line of code:
`const todoStorage = []`: this creates an empty array (which will store all the todos entered by the user)
- now let's break the 2nd line of code in 2 parts:
 - `localStorage.setItem("TODO-app storage",`: this piece of code creates a storage named "TODO-app storage" in our localStorage. 
 - `JSON.stringify(todoStorage)`: this part will turn the data we put in the storage into strings.
Let's not forget that **everything is a string in localStorage** BUT in our JavaScript code, under the hood, our data is actually in JSON format (JavaScript Object Notation). So it HAS to be turned into strings in order to be stored in localStorage. 
To do that, thankfully we have the built-in `JSON.stringify()`  method!
(Now is the moment you might ask: "so, to retrieve the data from localStorage we will need to do the opposite, right? turn the strings back into JSON format?" yes absolutely!!! you got it!
It gets done using the `JSON.parse()` method.
We'll use it shortly.)

At this point, if we check our localStorage, we see this🤩:
![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/7mv5yf2zj3z5wqg0k1iv.png)
Our storage is called "TODO-app storage" as we wanted, and it is an empty array `[]`. 

**<a name="2">2- Let's store each new task added by the user, in the storage! </a>**

1- `const todo = { task: input.value };` : this is what the user types in the input and that we display on the screen. we declare a "todo" variable to be an object with a property we choose to call "task", which stores the value (the text) that gets typed in the input by the user. 
2- `todoStorage.push(todo);` : easy array method `push()`to add the todo to the array todoStorage, the empty one we created earlier. 
3- `localStorage.setItem("TODO-app storage", JSON.stringify(todoStorage));` : now we set the Local Storage content to be that of our array todoStorage!
let's wrap all that in a function that we could call storeTodos():
```
function storeTodos(){
const todo  = {task: input.value};
todoStorage.push(todo);
localStorage.setItem("TODO-app storage", JSON.stringify('todoStorage'));
}
```

Let's invoke that function when the submit button is clicked for example!
We should see our localStorage in action!

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/5yu0xec1wa8vuwc7esq7.gif)

**<a name="3">3- Let's display all the todos stored in the localStorage after the user refreshes the browser or even closes the window and comes back!</a>**

We'll manage to do that in 2 steps:
1- a function to display the todos:
```
function displayTodos() {
 const todoStorage = JSON.parse(localStorage.getItem('TODO-app storage')) || [];
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
Quick breakdown of this code:
- `JSON.parse(localStorage.getItem('TODO-app storage'))` : this is the JSON.parse() method we were talking about earlier! **When we save data to the storage: we need to JSON.stringify().** 
**when we get our data from the storage, we need to JSON.parse().** 
- `||[]` : it means todoStorage is either the JSON.parse() of todoStorage (which means it exists) OR `||` it's an empty array (if nothing has been stored yet)
- As you can see the rest is a DOM manipulation using template literal (very handy to render dynamically created HTML) + the insertAdjacentHTML() method!
- both `<i class="far fa-square"></i>` and `<i class="far fa-trash-alt"></i>` are from Fontawesome! The `<i>` tags mean "icon" and allow us to display Fontawesome library icons!
If you don't know Fontawesome, click [here](https://fontawesome.com/icons?d=gallery) to check it out! 

2- adding an event listener to the window to detect when the page gets refreshed (or closed and reopened). It is called the **DOMContentLoaded** event. It's another event we can listen too, just like 'click' or 'keydown'! 
We'll invoke the displayTodos function at that moment:
```
window.addEventListener('DOMContentLoaded', displayTodos);
```
![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/3d0o6vwmbuab2evm3vn8.gif)
Aaand that's a wrap!! The users of our TODO-app can refresh the page or close and reopen the browser: their list will still be on screen, like a real application!😎

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/01r05byepibxy5knvwrl.gif)
That was it for today about the Local Storage! 
I hope this article was somewhat helpful or that it could give you some inspiration/ideas for your own projects.

Let me know in the comments below if there's any aspect you would like me to develop further or if you have any question/remark/suggestion.

For now, thank you for reading.

Next article next week!🤙🏾







 


  





  


