#JVFloat.js - [Demo](http://bootsnipp.com/iframe/OvV)
[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/maman/jvfloat.js/trend.png)](https://bitdeli.com/free "Bitdeli Badge")  

jQuery and Zepto plugin to emulate the behavior of [JVFloatLabeledTextField](https://github.com/jverdi/JVFloatLabeledTextField) which based on the concept from [Matt D. Smith](http://dribbble.com/shots/1254439--GIF-Mobile-Form-Interaction?list=users).
Read more on [The Blog post](http://blog.mahardi.me/2013/10/14/jvfloatjs---the-experiment-with-form-accessbility-and-ux-in-html5/)

Please note that JVFloat has very basic styles, and only provide the logic of the implementation. view [jvfloat.css](https://github.com/maman/JVFloat.js/blob/master/jvfloat.css) to see the styles used in the default theme. happy hacking! :thumbsup:

#Docs
Before you begins, make sure you have included [jQuery](http://jquery.com) or [Zepto.js](http://zeptojs.com) on your page.

## Installation
JVFloat consist of two parts, `jvfloat.js` and `jvfloat.css`. the minified version of the script also avalaible on `jvfloat.min.js`. to use JVFloat.js on your page, include JVFloat *after* you load jQuery or Zeptojs, for example:
```html
<head>
	....
	<link rel="stylesheet" href="css/style.css">
	<link rel="stylesheet" href="css/jvfloat.css">
</head>
<body>
	....
	<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.0/jquery.min.js"></script>
	<script src="js/jvfloat.min.js"></script>
</body>
```
I strongly advise you to modify the default CSS file to reflect your current page, as the default CSS only consists the essential element that makes the placeholder showing and hiding animations. Please read the full CSS documentations avalaible below before you make any edit to the CSS file.  

Now JVFloat is installable via [Bower](http://bower.io): `bower install JVFloat`

## Initialization
JVFloat can be initialized by calling `jvFloat()` functions, for example:
```html
<script>
	$('.testBox').jvFloat();
</script>
```
by default, JVFloat.js won't process `submit` buttons, and automatically exclude it from being transformed.
## CSS Documentation

### `.jvFloat`
this section performs styling on the `div.jvFloat` wrapper around the `input` generated by the script.  
**Rules that you mustn't remove**: `position: relative;`

### `.jvFloat .placeHolder`
this section performs styling on the `span.placeHolder` element inside `div.jvFloat`, where the copy of `input` placeholder text was stored. it's hidden by default.  
**Rules that you mustn't remove**: `position: absolute;`, `display: none;`, `visibility: hidden;`, `opacity: 0;`

### `.jvFloat .placeHolder.required`
the styling of the `required` placeholder. The default color is simply `red`.

### `.jvFloat .placeHolder.active`
the active state of the aftermentioned section. its job are to display the hidden `span.placeHolder` when users is typing on the `input`.  
**Rules that you mustn't remove**: `display: block;`, `visibility: visible;`, `opacity: 1`

## Another Notes on CSS
JVFloat uses CSS3 [Transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) and [Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) to perform the animations by default. Browsers that doesn't support those will simply doesn't show anything when user typing on the `input` elements. to fix that, enable/uncomment the `legacy` rules on the default CSS file, and comment out the `CSS3` rules.

#TODO
* ~~Better CSS Animations~~ *need your suggestion on this one, btw*
* Better plugin code
* ~~Write better docs~~

#Changelog

* 15/04/2014 - Release first stable version of JVFloat.js . add ability to redefine CSS on multiline `textarea`, thanks to @Jackobyte for the pull request. Also now JVFloat has a grunt-based build system.
* 31/01/2014 - JVFloat now uses actual `<label>` elements to improve accessbility. thanks to @MrSnowflake for the pull request
* 21/12/2013 - Code refactoring. thanks to @eskimoblood for the pull request
* 11/08/2013 - Add animation when user switch to another form element, thanks to @gabceb for the pull request.
* 10/23/2013 - Fix the bug where JVFloat process all `input` elements, including `submit`, fix the animations &mdash; it's noticeably smoother! &mdash;, add support for `required` inputs, and I'm adding more detailed documentations.
* 10/12/2013 - First Commit
