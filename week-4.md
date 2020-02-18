# Week 4: Events and Interactions

HTML Events

* All events occur on HTML elements in the browser
* JavaScript is used to define the _action_ that needs to be taken when an event occurs

```text
When [HTML EVENT], do [JS Action]
```

Adding Action Listeners in HTML

* To show that actions originate from HTML elements, we can put attributes inside of elements

```text
<div onclick=“alert(‘Clicked!’)”>...</div>
```

Setting Up Listeners in JS

* An event listener in JS programmatically sets an event attribute on a HTML element
* Select an element in JS, and then:

```text
element.addEventListener(event, functionToExecuteWhenEventOccurs)
```

The functionToExecuteWhenEventOccurs, is a 'callback' function. So essentially:

> element.addEventListener\(event, callback\)

Callback Functions

* A callback is a function that is designated to be 'called back' at an appropriate time
* In the case of events, it will be 'called back' when the event occurs
* Can be an anonymous function, or a function defined outside of the event listener

```text
button.addEventListener('click', function() { alert('Clicked') });

function alertClick() { alert('Clicked') }
button.addEventListener('click', alertClick);
```

Event Objects

* All events that occur create a JS Object with information about the event:
  * Event.target - event origin element
  * Event.type - type of event
* Passed to the callback function as argument

```text
function myCallback(e) {
    // figure out where e came from
    // execute proper code
}
```

Common Events

* onChange - a HTML element has been changed
* onClick - the user clicks a HTML element
* onMouseOver - the user moves the mouse over a HTML element
* onMouseOut - the user moves the mouse away from a HTML element
* onKeyDown - the user pushes a keyboard key
* onKeyUp - the user releases a keyboard key
* onLoad - the browser has finished loading the page

Non-Blocking JS - Asynchronous Programming

* Blocking code: code that runs one instruction after another, and makes next instructions wait \(block\)
* Non-blocking code allows JS to continue executing instructions while we wait for some blocking code to complete
  * e.g. setTimeout\(\)
  * Will execute instructions immediately after setTimeout\(\) is called without waiting for it to finish

JS Runtime Engine

* JavaScript must be 'compiled' and interpreted so it needs a runtime environment
* JavaScript is an event-driven language; how does it keep track of all of these events? Event Loop

How many threads?

* JavaScript is single-threaded: only runs one thing at a time
* The event loop helps with dealing with asynchronous stuff through scheduling events one after the other with the help of the platform that is multi-threaded \(i.e., browser\)

JavaScript Event Loop

* A way of scheduling events one after another
* Often with the help of the platform the engine is running on
* Non-blocking functions aren't built in to the V8 runtime

Check out [Loupe](http://latentflip.com/loupe/?code=JC5vbignYnV0dG9uJywgJ2NsaWNrJywgZnVuY3Rpb24gb25DbGljaygpIHsKICAgIHNldFRpbWVvdXQoZnVuY3Rpb24gdGltZXIoKSB7CiAgICAgICAgY29uc29sZS5sb2coJ1lvdSBjbGlja2VkIHRoZSBidXR0b24hJyk7ICAgIAogICAgfSwgMjAwMCk7Cn0pOwoKY29uc29sZS5sb2coIkhpISIpOwoKc2V0VGltZW91dChmdW5jdGlvbiB0aW1lb3V0KCkgewogICAgY29uc29sZS5sb2coIkNsaWNrIHRoZSBidXR0b24hIik7Cn0sIDUwMDApOwoKY29uc29sZS5sb2coIldlbGNvbWUgdG8gbG91cGUuIik7!!!PGJ1dHRvbj5DbGljayBtZSE8L2J1dHRvbj4%3D)

