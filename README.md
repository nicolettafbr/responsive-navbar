# Responsive Navbar
### Made with :sparkling_heart: by Nicoletta Fabro

## Overview
Responsive navigation bar component built with HTML and CSS. To achieve mobile navigation without using Javascript, the mobile menu uses a checkbox to toggle the menu.
This navbar was built following mobile-first principles. As such, all media queries are structured using minimum width as a starting point.

## Improvements
### GSAP
At the current state of development, whenever going from desktop to mobile with the checkbox in the unchecked state (which corresponds to only the hamburger icon showing in the mobile version) the menu transitions for a second from open to closed, instead of staying closed. This is mainly due to the animation being reliant on the menu itself rather than on an event emitted.
In order to solve this, I am planning to listen to the DOM click event and use GSAP to open and close the mobile menu.
### Sass
To improve on readability and ease of development I am planning to migrate from CSS to Sass.

## Final Result
Currently, the navigation bar behaves as follows:

![responsive Navbar Video](https://github.com/nicolettafbr/responsive-navbar/blob/main/responsive-navbar.gif)

You can try it yourself on [Codepen](https://codepen.io/nicolettafbr/pen/KKNydVK).

For any suggestion on the matter, please do not hesitate to contact me. Enjoy! :smile:
