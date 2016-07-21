###How to use CSS3 Transition and Transforms for Animating Menu "hamburger" icon
**Demo**: 
- http://trungk18.github.io/demo/animated-navigation-menu-icons-with-css3.html
- http://codepen.io/trungk18/pen/jrrXjz

In this demonstration, I will show you how to create an hamburger icon and put some simple animations when clicking.

####How To Create a Menu Icon

######HTML
```html
<div class="container">
    <span class="bar bar1"></span>
    <span class="bar bar2"></span>
    <span class="bar bar3"></span>
</div>
```

######CSS
```css
.icon-container {
    float: left;
    position: relative;
    cursor: pointer;
    margin: 0 5em 5em;
    -webkit-transition: all 0.3s;
    -moz-transition: all 0.3s;
    transition: all 0.3s;
}

.bar {
    display: block;
    width: 35px;
    height: 5px;
    background-color: #333;
    margin: 6px auto;
    transition: 0.3s;
    border-radius: 3px;
}
```

It is pretty straight forward, using *width* and *height* specify for each bar and *margin* make some distance between them. Then we put three bar together, covered by a container.

####How To Create Animated Menu Icon

######HTML
```html
    <div class="container" onclick="toggleMenu(this)">
        <span class="bar bar1"></span>
        <span class="bar bar2"></span>
        <span class="bar bar3"></span>
    </div>
```

######CSS
```css
    /*Rotate first bar*/
    .change .bar1, .change .bar4 {
        -webkit-transform: rotate(-45deg) translate(-9px, 6px);
        transform: rotate(-45deg) translate(-9px, 6px);
    }

    /*Fade out the second bar*/
    .change .bar2 {
        opacity: 0;
    }

    .change .bar5 {
        width: 0%;
    }

    /*Rotate last bar*/
    .change .bar3, .change .bar6 {
        -webkit-transform: rotate(45deg) translate(-8px, -8px);
        transform: rotate(45deg) translate(-8px, -8px);
    }
```
######JS
```javascript
	function toggleMenu(x) {
		x.classList.toggle("change");
	}
```
We keep using the same class *.bar* with transition in 0.3s. And the important thing is adding class name for each bar. You can see bar1 to bar6 class.
When the button is clicked on, *toggleMenu()* will be executed to toggle class *.change* to make magic happens.
* bar1 will be rotated 45 degree counter-clockwise 
* bar2 will be faded out then disappeared
* bar3 will be rotated 45 degree clockwise

Please check the image below for detail explanation of CSS rotate and translate(x,y)

![How to use CSS3 Transition and Transforms for animating menu "hamburger" icon with CSS3](http://trungk18.github.io/demo/explanation/animated-navigation-menu-icons-with-css3-explain.png)

####Conclusion
Nowadays hamburger icon is in used widely, I often using Font Awesome to get this one but If we want to put more awesome and impressive animation purpose, we must write our own HTML and CSS. I hope you enjoy this demo. 
Thanks for checking it out and view the demo, feel free to fork and fix the source code then pull back to me.
