![Bower version](https://badge.fury.io/bo/swf-jquery.svg)

# ![swfJQ Logo](http://i.imgur.com/Wed19Q4.png)

jQuery plugin that easily manipulate SWF based on SWFObject.

This awesome class exist since 2009. Now on Bower.

### Quickstart

Using [Bower](http://bower.io)
```
bower install swf-jquery --save
```

### Demo 
[http://webcaetano.github.io/swf-jquery/](http://webcaetano.github.io/swf-jquery/)

# Documentation


  - [$(selector).flash()](#$(selector).flash())


### $(selector).flash()

Load flash swf on the select

```javascript
$('#div1').flash('myFlash.swf');
```

### Load with Parameters

Load a flash swf with parameters.

flashvars accept *string,boolean,number* 

for *object* and *array* use JSON.stringify() and JSON.parse() on actionscript

```javascript
$('#div1').flash({
	swf: 'myFlash.swf',
	height: 400, // stage Height
	width: 600, // stage width
	allowFullScreen: true,
	wmode: 'transparent', // background transparent
	flashvars: { // set Flash variables 
		players: 2,
		computer: true,
		foo: 'bar',
		obj: JSON.stringify({name:'TheOddOne',arr:[1,2,3]})
	}
});
```

### $.flash.available

Return a boolean value based on availability Flash plugin.

```javascript
return $.flash.available; // returns true if Flash plugin available
```

### $.flash.version

Return a object containing version information about the the user's Flash plugin. 

```javascript
return $.flash.version

/* returns {
	"original":"Shockwave Flash 17.0 r0",
	"array":["17","0","0"],
	"string":"17.0.0",
	"major":17,
	"minor":0,
	"release":0
}*/
```

### $.flash.hasVersion()

A function which returns a boolean value of whether the user has installed the minimum specificed version of the Flash plugin.

```javascript
return $.flash.hasVersion(9.1); // returns true if at least Flash 9.1 or greater is detected
```

### $.flash.activeX

A boolean value of whether the browser uses Flash via activeX.

```javascript
return $.flash.activeX; // returns true or false
```

### $.flash.expressInstaller

A string that sets the filename of the express installer that will always be used.

```javascript
$.flash.expressInstaller = 'myFlashPath/expressInstall.swf'; // changes the express installer
```

### $.flash.encodeParams

A boolean value of whether the params will always be URI encoded.

```javascript
$.flash.encodeParams = false; // default is true
```

### $.flash()

A function which returns a standards-friendly jQuery'd flash object.

```javascript
var useLater = $.flash.create({
	swf: 'myFlash.swf',
	height: 400,
	width: 600
});

$(document).ready(function(){
	$.('#putFlashHere').html(userLater);
});
```

#### Project to-do list.

- [x] Setup to bower.
- [x] Create Demo in [githubPages](https://pages.github.com/)
- [x] Finish documentation.
- [ ] Create swfZepto


#### Authors
[@jonathantneal](https://github.com/jonathantneal)

[@webcaetano](https://github.com/webcaetano)
