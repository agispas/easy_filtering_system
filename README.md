# [Easy content filtering](http://agispas.com/easy_filtering_system) - [jQuery]()

Many times when I had to implement a live search and a filtering system, I had to use plugins which were way too extensive and bloated with tons of features and many pages of documentation. 
There are plenty of plugins which will do these things, some of them are free and also widely supported, I’m not trying to show you just another filtering system.

This is a  basic way to create a filtering system using a live search plugin with just few lines of code. 

So, if you’re looking for a full list of features, functionalities, animations, event handlers, there are plugins which can do that, this article is not about that.

### Let’s begin!

We will use HideSeek which is a simple, yet customizable jQuery plugin for live search, is compatible with IE7+, Chrome, Firefox, Safari and jQuery 1.8.1, 1.9.1, 1.11.0, 2.1.0. and supports highlighting, custom message, navigation, initialization via data attribute and custom events.
Configuring it is pretty simple, here’s the default usage: use this template, choose one of the following options to get started:
```
$(‘#search’).hideseek();
```
Basically you have to declare the id, class or whatever for your input element, in my case the search input.
This is how the search input looks:
```
<input id=”search” name=”search” placeholder=”Start typing here” type=”text” data-list=”.sorting_list” autocomplete=”off”>
```
You see here data-list=”.sorting_list” this is where we choose what content to search.
My list consists of some images and some text.
The markup is pretty simple, nothing complicated. It’s just for providing a simple use case:
```
<! — Projects Row →
 <div class=”row”>
 <ul class=”sorting_list”>
 <li>
 <div class=”col-md-4 portfolio-item”>
 <a href=”#”>
 <img class=”img-responsive” src=”img/cow.png” alt=””>
 </a>
 <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam viverra euismod odio, gravida pellentesque urna varius wonder cow.</p>
 </div>
 </li>
 </ul>
 </div>
 <! — /.row — >
 ```
How this works till now I think is pretty easy to understand. If you write “cow” inside the search input you will see just the cow image and the text associated with it.

### Now, the fun part. A filtering system based on the search input.
As you probably noticed, in the screenshot above we have few links like “Mighty Bird”, “Nerdy Cat”, “Wonder Cow”.
Next we’re going to make the anchor elements behave like filters. For example when we click on “Mighty Bird” the search input will be filled with the text “Mighty Bird”.
We have “View all” which I don’t have to explain what it does.

Have a bug or an issue with this template? [Open a new issue](https://github.com/IronSummitMedia/startbootstrap-2-col-portfolio/issues) here on GitHub or leave a comment on the [template overview page at Start Bootstrap](http://startbootstrap.com/template-overviews/2-col-portfolio/).

## The magic:
 ```
$(document).ready(function() {
 
 jQuery(‘a.clear ‘).on(‘click’, function(event) {
 $(‘input#search’).val(‘’).trigger(‘keyup’);
 });
 jQuery(‘a.filter ‘).on(‘click’, function(event) {
 jQuery(‘input[name=”search”]’).val($(this).text().trim());
 jQuery(‘input[name=”search”]’).keyup();
 });
});
 ```
First we make sure that if the link with a class name of “clear” is clicked we clear the search input.
Next we check if a link with a class name of “filter” is clicked we add to the search input the anchor element text.

## Pretty simple, no?

We now have a fully functional filtering system with just few lines of code. You don’t have to add heavy weight plugins with tons of features if you just want something simple like this.
That’s it! We have just built a quick and easy content filtering using a live search jQuery plugin.

## [Demo](http://agispas.com/easy_filtering_system)
