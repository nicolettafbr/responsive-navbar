# Responsive Navbar
### Made with :sparkling_heart: by Nicoletta Fabro

## Overview
Responsive navigation bar component built with HTML and CSS. To achieve mobile navigation without using Javascript, the mobile menu uses a checkbox to toggle the menu.
This navbar was built following mobile-first principles. As such, all media queries are structured using minimum width as a starting point.

## Improvements
At the current state of development, whenever going from desktop to mobile with the checkbox in the unchecked state (which corresponds to only the hamburger icon showing in the mobile version) the menu transitions for a second from open to close, instead of staying closed. This is mainly due to the animation being reliant on the menu itself rather than on an event emitted.
In order to solve this, I am planning to listent to the DOM click event and use GSAP to open and close the mobile menu.

## Final Result
```
<div class="codepen" data-height="361" data-theme-id="dark" data-default-tab="html,result" data-user="nicolettafbr" data-slug-hash="KKNydVK" data-preview="true" data-prefill='{"title":"Responsive Navigation Bar","description":"Responsive navigation bar component built with love using HTML and CSS. To achieve mobile navigation without using Javascript, the mobile menu uses a checkbox to toggle the menu.\nThis navbar was built following mobile-first principles. As such, all media queries are structured using minimum width as a starting point.","tags":["responsive","navbar","menu","html","css"],"scripts":[],"stylesheets":[]}'>
  <pre data-lang="html">&lt;!--    Made by Nicoletta Fabro    -->
&lt;nav role="navigation">
  &lt;div id="menuToggle">
    &lt;!--
    A fake / hidden checkbox used as click reciever¬.
    -->
    &lt;input type="checkbox" />
    
    &lt;!--
    Some spans acting as the hamburger icon.
    These will be animated into a cross when clicked.
    -->
    &lt;span>&lt;/span>
    &lt;span>&lt;/span>
    &lt;span>&lt;/span>
    
    &lt;!--
    The menu itself.
    -->
    &lt;ul id="menu">
      &lt;a href="#">&lt;li>Home&lt;/li>&lt;/a>
      &lt;a href="#">&lt;li>About&lt;/li>&lt;/a>
      &lt;a href="#">&lt;li>Contacts&lt;/li>&lt;/a>
      &lt;a href="#">&lt;li>Show me more&lt;/li>&lt;/a>
      &lt;div class="underbar">&lt;/div>
    &lt;/ul>
  &lt;/div>
&lt;/nav></pre>
  <pre data-lang="css">body
{
  margin: 0;
  padding: 0;
  
  background: #ffffff;
  color: #232323;
  font-family: 'Poppins', sans-serif;
}

#menuToggle
{
  display: block;
  position: relative;

  padding: 30px;
  
  z-index: 1;
  
  -webkit-user-select: none;
  user-select: none;
}

#menuToggle a
{
  text-decoration: none;
  color: #ffffff;
  
  transition: color 0.3s ease;
}

#menuToggle a:nth-of-type(1):hover
{
  color: #F062C3;
}

#menuToggle a:nth-of-type(2):hover
{
  color: #36FAFF;
}

#menuToggle a:nth-of-type(3):hover
{
  color: #DB731F;
}

#menuToggle a:nth-of-type(4):hover
{
  color: #587AF5;
}

#menuToggle input
{
  display: block;
  position: absolute;
  width: 25px;
  height: 20px;

  margin: 0;
  padding: 20px;
  
  cursor: pointer;
  
  opacity: 0; /* Hides the checkbox */
  z-index: 2; /* Places the checkbox over the hamburger icon */
  
  -webkit-touch-callout: none;
}

/*  Styling the hamburger */
#menuToggle span
{
  display: block;
  width: 18px;
  height: 2px;
  margin-bottom: 4px;
  position: relative;
  
  background: #232323;
  border-radius: 3px;
  
  z-index: 1;
  
  transform-origin: 4px 0px;
  
  transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0), /* was 0.5s */
              background 0.5s cubic-bezier(0.77,0.2,0.05,1.0), /* was 0.5s */
              opacity 0.55s ease; /* was 0.55s */
}

#menuToggle span:first-child
{
  transform-origin: 0% 0%;
}

#menuToggle span:nth-last-child(2)
{
  transform-origin: 0% 100%;
}

/* 
 * Turns the hamburger slices into a crossmark when clicked
 */
#menuToggle input:checked ~ span
{
  opacity: 1;
  transform: rotate(45deg) translate(1px, 3px);
  background: #ffffff;
}

/* Hides the middle slice */
#menuToggle input:checked ~ span:nth-last-child(3)
{
  opacity: 0;
  transform: rotate(0deg) scale(0.2, 0.2);
}

#menuToggle input:checked ~ span:nth-last-child(2)
{
  transform: rotate(-45deg) translate(0, 0);
}

/* Positions the menu absolutely at the top left of the screen */
#menu
{
  position: fixed;
  top: 0;
  left: 0;

  width: 100vw;
  height: 100vh;
  margin: 0;
  padding: 30px;
  padding-top: 80px;
  
  background: #232323;
  list-style-type: none;
  /* Stops the flickering of text in Safari */
  -webkit-font-smoothing: antialiased;
  
  transform-origin: 0% 0%;
  transform: translate(-100%, 0);
  
  transition: transform 0.5s cubic-bezier(0.77,0.2,0.05,1.0);
}

#menu li
{
  padding: 10px 0;
  font-size: 16px;
}

/* Slides the menu in from the left! */
#menuToggle input:checked ~ ul
{
  transform: none;
}

/* Media queries for a seamless user experience.
** Tablets
*/
@media only screen and (min-width: 768px) {
  #menuToggle input, #menuToggle span {
    display: none;
  }

  #menu {
    display: flex;
    flex-direction: row;

    background: #ffffff;

    padding: 0;
    padding-left: 15px;
    height: auto;

    transform: none;
    transition: none;
  }

  #menu li {
    padding: 15px;
  }

  #menuToggle a {
    color: #232323;
  }

  .underbar {
    position: absolute;
    top: 45px;
    left: -10px;

    width: 0;
    height: 4px;
    background: rgba(100,100,200,0);
    -webkit-transition: 0.5s ease;
  }

  #menuToggle a:nth-of-type(1):hover ~ .underbar {
    left: 28px;;
    width: 48px;
    background: rgba(240,98,195,1);
  }

  #menuToggle a:nth-of-type(2):hover ~ .underbar {
    left: 100px;;
    width: 48px;
    background: rgba(54,250,255,1);
  }

  #menuToggle a:nth-of-type(3):hover ~ .underbar {
    left: 172px;;
    width: 68px;
    background: rgba(219,115,31,1);
  }

  #menuToggle a:nth-of-type(4):hover ~ .underbar {
    left: 265px;;
    width: 112px;
    background: rgba(88,122,245,1);
  }
}

/*  Small desktops */
@media only screen and (min-width: 992px) {

}

/*  Big destops */
@media only screen and (min-width: 1020px) {

}</pre></div>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
```
