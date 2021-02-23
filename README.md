# Responsive Navbar
### Made with :sparkling_heart: by Nicoletta Fabro

## Overview
Responsive navigation bar component built with HTML and CSS. To achieve mobile navigation without using Javascript, the mobile menu uses a checkbox to toggle the menu.
This navbar was built following mobile-first principles. As such, all media queries are structured using minimum width as a starting point.

## Improvements
At the current state of development, whenever going from desktop to mobile with the checkbox in the unchecked state (which corresponds to only the hamburger icon showing in the mobile version) the menu transitions for a second from open to close, instead of staying closed. This is mainly due to the animation being reliant on the menu itself rather than on an event emitted.
In order to solve this, I am planning to listent to the DOM click event and use GSAP to open and close the mobile menu.

## Final Result
[Codepen](https://codepen.io/nicolettafbr/pen/KKNydVK)
