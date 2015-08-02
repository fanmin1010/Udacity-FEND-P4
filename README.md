## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository, inspect the code,

### Getting started

####Part 1: Optimize PageSpeed Insights score for index.html

To achieve a PageSpeed Insight score above 90 for both mobile and laptop, the following changes have been made.

1. Since all the external javascript files are not modifying the DOM/CSSOM, they should not be parse-block. Therefore they are all set to be async.

2. External CSS files have been modified. One critical CSS file was inlined to prevent it from render-blocking. The other css file is only used for print, so the media attribute has been added to the tag.

3. All the images for loading have been optimized and compressed using grunt.

####Part 2: Optimize Frames per Second in pizza.html

The following modifications have been made to js/main.js in pizza.html.

1. The computation efficiency was optimized for pizza.html in resizing pizzas. By using a simpler calculation method for resizing, forced synchronous layout has been avoided. There fast calculations have been achieved.

2. In the updatePosition function, which were designed to change locations of moving pizzas when the page was scrolled, requestAnimationFrame was used to mimic animation. Also codes have been modified to avoid forced synchronous layout. More importantly, the number of moving pizzas item has been significantly reduced, since originallly huge amount of the moving pizza items are not even shown on the page.