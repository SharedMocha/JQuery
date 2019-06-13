# JQuery
JQUERY
JQUERY-->JavaScript is the most widely-used language for adding dynamic behavior to web pages. The JavaScript community contributes to a collection of libraries that extend and ease its use. In this course, you will learn about jQuery, a JavaScript library that makes it easy to add dynamic behavior to HTML elements.
KNOW JQUERY EFFECTS BELOW--https://api.jquery.com/category/effects/
*Let’s use Legos as an analogy for understanding how jQuery works. With an infinite number of Legos, you could build an entire city — of course, this would take a long time. What if you were given pre-made Lego buildings, Lego roads, Lego parks, etc? You could build a city much faster.
**https://s3.amazonaws.com/codecademy-content/courses/jquery/images/jquery-diagrams_webpage-buildingblocks.svg
*The $ symbol is an alias for the jQuery function. The $ symbol and jQuery are interchangeable.
**IN JQUERY U USE NAME,CLASS,ID,.currentTarget,children position -> ways to target elemnts and update them

*you can add jquery at bottom of body using -  
   <script
  src="https://code.jquery.com/jquery-3.2.1.min.js"
  integrity="sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4="
  crossorigin="anonymous"></script>
* .ready() ->The jQuery .ready() method waits until the HTML page’s DOM is ready to manipulate. You should wrap all JavaScript behavior inside of the .ready() method. 
  $(document).ready(() => {

});


SYNTAX EXPLANATION-
In the example above, document is a special keyword that we use to target the HTML document and create a jQuery object.
We can use the same $() syntax to create jQuery objects for elements on a web page. Typically, we pass a string into $() to target elements by id, class, or tag. Once targeted, we can use . notation to attach a handler method that triggers a callback function.
*$('.someClass').handlerMethod(); //TARGETINY BY CLASS WITH A METHOD
*$('#someId').hide(); //TARGETING BY ID to hide it
*The jQuery or $ (interchangable) function takes a parameter that targets an element, like '#navMenu', and turns it into a jQuery object. Then, you can call any jQuery method on a jQuery object.
const $jQueryObject = $('.someClass'); or jquery('.someClass');
Notice our variable name, $jQueryObject, starts with the ($) character. It is best practice to name jQuery object variables with a leading $. It is a naming convention that reminds you and lets others know that a given variable is a jQuery object.
*event handlers -> using.on() method
$('#login').on('click', () => {
  $loginForm.show(); //this is a jquery object that poihts to some html elment..
})


*JQUERY SELECTORS aprt from id,class,name,.currentTarget --
 ** children -> get parent and save in a object and then call its children //const $kids = $('#holder').children(); //$kids.on('click', event => {$(event.currentTarget).css('border', '1px solid black');});
 ** .parent() -> parent targets the given elments partens and modifies it // $('.choice').on('click', event => {$(event.currentTarget).parent().hide();}); //hide .choice parent
 ** .siblings() -> (used in menu items like show the color ion clicked item and also remove color from old item that is clicked)tagrgets adjacemt elment and updates them //$('.choice').on('click', event => {$(this).siblings().removeClass('selected');$(event.currentTarget).addClass('selected');}); //In the code above, the .siblings() method targets elements adjacent to the clicked '.choice' and removes the 'selected' class from any previously clicked '.choice's. Then the 'selected' class is added only to the clicked '.choice'.
 ** .closest() ->(ex-highight add to cart only when an quanity is selected)To select an element close to the current element, we can use jQuery’s .closest() method. the .closest() method will travel up the DOM tree to find a specified selector closest to it. Its syntax looks like: //$('.example-class-one').closest('.another-class');
 ** Next() & .prev()  ->Sometimes you don’t want to target all the siblings of an element — you just want to target the next one. That’s where the aptly-named .next() method comes in //  $(event.currentTarget).next().toggle();
 **find() ->Sometimes we want to target an element that lives inside another, but we don’t want to use the .children() method, since that might target more elements than we need. That’s where the .find() method comes in. This method finds and targets singular or multiple elements that are descendants of an element. Unlike the .children() method, it traverses all descendants of the specified element, not just the first level down. //
   const $items = $('.myList').find('li'); //The .find() method takes a parameter that specifies how to filter results. This parameter is just like anything you might use to select a jQuery object, ('#id', '.class', tag, etc.). .find() will return all descendants that match the passed in selector. In the example above, the .find() method will return all <li> child elements inside the '.myList' element.

 
CSS **to modify css -jquery give .css for us -> $('.example-class').css('color', '#FFFFFF',  backgroundColor: '#000000',);
  **.animate() //css animate kind of   $('.example-class').animate({height: '100px',width: '100px',borderWidth: '10px'}, 500);
  ** .addClass() // instead of you always updating styles as above..which is not good..define a css class and keep adding and removing it--its better and good practise.. $('.example-class').addClass('active');
  ** .removeClass() //REMOVE CLASS //$('.example-class').removeClass('active');
  ** .toggleClass() //$('.example-class').toggleClass('active');//Similar to other effects methods, you can use a toggle method instead of chaining the .addClass() and .removeClass() methods together. The .toggleClass() method adds a class if an element does not already have it, and removes it if an element does already have it. Its syntax looks like:


*jQuery Effects are a group of methods in the jQuery library that are responsible for adding dynamic behavior to websites
  ** .hide() //When you hide an element, your browser will render the HTML as if the hidden element does not exist. It will disappear from the page and the space that it was taking up will disappear as well. Take a look at the code below to learn how to use the .hide() method:
  ** .show()  //the .show() method does the opposite of .hide(). If an element on your page is hidden, .show() will make it appear.//$('.show-arrow').on('click', () => {$('.shoe-information-2').show();});
  ** .toggle() // Great work! Our table now has two buttons that hide and show our image. But wouldn’t it be nice to have one button do both? It is common for web pages to have one button that will either hide or show elements depending on their current state. We can achieve this by using the .toggle() method.
  ** .fadeIn(),.fadeOut() //$('div').fadeOut(1000); Both .fadeIn() and .fadeOut() take an optional parameter that specifies how long the animation will take. For example, in the code below, all <div> elements will fade out over a period of 1000 milliseconds (or one second).
  **.fadeToggle() //  If you call .fadeToggle() on an element that is invisible, it will fade in. And if the element is already visible, then .fadeToggle() will make it fade out.
  **.slidedown or slideUp  -used for menu //$('.menu-button').on('click', () => {$('.menu-content').slideDown('slow');}); //By using sliding effects, an element on your web page will slide up or down into place instead of appearing or disappearing. Just like with the other effects, sliding can be applied to any element on your page whether it be an image, a video, or text.
*jquery mouse events-
  ** mouseenter //$('.example-class').on('mouseenter',  () => {    // Execute code here when mouse enters .example-class});
  ** mouseleave
  ** currentTarget // target single elemnt...lets say we have images and onenter we need to zoom it..by default going onto one will zoom all..so to avoid use currenttarget to get current images target and only enlarge it
  $('.example-class').on('mouseenter', event => {
  $(event.currentTarget).addClass('photo-active');
  });
*jquery chain multiple events- like click and enters

Before Jquery ->
const login = document.getElementById('login');
const loginMenu = document.getElementById('loginMenu');

login.addEventListener('click', () => {
  if(loginMenu.style.display === 'none'){
    loginMenu.style.display = 'inline';
  } else {
    loginMenu.style.display = 'none';
  }
});


After Jquery ->
$('#login').click(() => {
  $('#loginMenu').toggle()
});



---------------------------------------------------------------------------------------------------------
In this lesson, you learned:

About JavaScript libraries.
How to add jQuery to your web page.
How to avoid loading errors with the .ready() method.
About jQuery objects and their methods.
How to target elements by id and class.
Naming conventions for storing jQuery objects in JavaScript variables.
How to add event handlers with .on().
A couple jQuery effects, such as .hide() and .show().
----------------------------------------------------------------------
JQUERY EFFECTS->
Review: Effects
Wow! You’ve completed this table of 9 different jQuery effects. Great job! To review, the methods that we learned were:

.hide()
.show()
.toggle()
These methods instantly hide or show elements on a web page.

.fadeOut()
.fadeIn()
.fadeToggle()
These methods make elements disappear or appear over a given period of time.

.slideUp()
.slideDown()
.slideToggle()
These methods make elements slide up or down into place over a given period of time.

Using these effects, you can make your web pages eye-catching and dynamic. And thanks to the magic of jQuery all of this can be done with very few lines of code!
--------------------------
MOUSE EVENTS
The jQuery library provides a collection of methods that serve one of two purposes.
*To listen for an event — an event (e.g. clicking a button) is something the user does to trigger an action.
*To add a visual effect — a visual effect (e.g. a drop-down menu appearing when a user clicks a button) is something that changes the appearance of the web page. Events are often responsible for triggering a visual effect.

$('.example-class').on('click', () => {
    // Execute code here when .example-class is clicked
});
Let’s consider the example above step-by-step:

$('.example-class') selects all HTML elements with a class of example-class.
The on('click') method is the event listener. It checks if the user has clicked an .example-class HTML element.
The second argument to .on() is a callback function. When a 'click' occurs on an example-class element, this function executes.

*currentTarget->
ave you noticed in our Sole Shoes website that when you mouse over one photo, all of the images zoom. That’s because .product-photo is a class on all the product photos.

One way to solve this issue is to give each HTML element a unique class and to write three mouseenter and mouseleave functions. That, however, would result in a lot of repetitive code. Luckily there’s a better way.

The solution is in the callback function and selector we’re using when we add a new class. Instead of selecting $('.product-photo') in each callback function, we need to pass event information into the function and call the currentTarget attribute:

$('.example-class').on('mouseenter', event => {
  $(event.currentTarget).addClass('photo-active');
});
The points below explain some of the features of the event.currentTarget selector in the example above.

When a user triggers the mouseenter event listener above, the .on() method generates an event object that we pass into the callback function.
Inside the callback function, we select event.currentTarget. The currentTarget attribute refers to only the .example-class element that the learner has moused over.
Since $(event.currentTarget) refers to the element that an event is detected on, you will only use it inside a callback function.



->
Review: Event Handlers
In this lesson, you learned a few of the most common mouse events in the jQuery library.

Event handlers are comprised of an event listener and a callback function. An event listener specifies the type of event that will be detected. The callback function executes when the event happens. Everything together is the event handler.
An event listener is set up using the .on() method.
The events listened for included: 'click', 'mouseenter', and 'mouseleave'.
In addition to event handlers, you learned how to use event.currentTarget to refer to the individual element that an event occurred on.
0>
--------
STYLE METHODS ----css and jquery---
n this lesson, you learned:

The .css() method can change style properties of an element.
The .css() method can accept multiple styles at once if you pass it a JavaScript object as its argument.
The .animate() method can change specific style properties over a period of time.
The .addClass() will add a CSS class to an element, and the .removeClass() method will remove a CSS class.
The .toggleClass() method will toggle a class on or off an element.

----------------DOM--TRAVELLING THROUGH  DOM-----
https://s3.amazonaws.com/codecademy-content/courses/jquery/images/jquery-diagrams_family-relationships.svg

jQuery makes it easy to target HTML elements by tag name, class, and id. We can also dynamically target a single element in a given class by accessing an event’s .currentTarget attribute. In this lesson, we’ll go even further. You will learn how to target elements based on their position relative to other elements.

you can get childer as below->
 html-
 <div class='parent' id='holder'>
  <div>Child <span>1</span></div>
  <div>Child <span>2</span></div>
  <div>Child <span>3</span></div>
</div>
 
 js--
 const $kids = $('#holder').children();
$kids.on('click', event => {
  $(event.currentTarget).css('border', '1px solid black');
});




--.children() to target an element’s child elements.
.siblings() to target elements adjacent to an element.
.parent() to target an element’s parent.
.closest() travels up the DOM tree from the current element to target the closest element with a given selector.
.next() to target the element immediately following the selected element.
.prev() to target the element that is immediately preceding the selected element.
.find() to target descendant elements by some selector, ie- class, id, tag etc.
