---
title: "Vanilla JS add event listener on multiple elements"
date: 2022-01-12T18:49:48-08:00

---
## In Vanilla JavaScript, there are multiple ways of addEventListener to elements.

### Add event listener  to one single element:

```
const btn = document.getElementById('btn-section-3');
btn.addEventListener('click', function (event) {
  console.time('id');
  event.preventDefault();
  const element = document.getElementById(event.target.dataset.target);
  element.scrollIntoView();
  console.timeEnd('id');
});

```
1. Getting the element based on its ID CSS selector;
2. Using addEventListener to listen for click event;
3. Starting a  performance timer to keep track of the speed;
4. Doing a simple scrollIntoView to have some animation.


### Vanilla JavaScript use addEventListener in a for loop:

```
document.querySelectorAll('.more-class').forEach((item) => {
  item.addEventListener('click', (event) => {
    console.time('more');
    event.preventDefault();
    const element = document.getElementById(event.target.dataset.target);
    element.scrollIntoView();
    console.timeEnd('more');
  });
});

```
1. Using querySelectorAll to get all items the class more-class;
2. Looping through the element;
3. Using addEventListener and add it again to each element.

### Vanilla JavaScript using addEventListener to multiple items using event bubbling:

```
document.addEventListener('click', function (event) {
  if (!event.target.matches('.btn-scroll-into')) return;
  console.time('bubbling');
  event.preventDefault();
  const element = document.getElementById(event.target.dataset.target);
  element.scrollIntoView();
  console.timeEnd('bubbling');
});

```
1. Using addEventListener on all elements to listen to clicks anywhere in the DOM;
2. Checking all children if the target match the class btn-scroll-into.

[Reference](https://daily-dev-tips.com/posts/vanilla-javascript-event-listener-on-multiple-elements/)
