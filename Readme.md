*This repository is a mirror of the [component](http://component.io) module [bredele/wall](http://github.com/bredele/wall). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/bredele-wall`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# Wall

[![Build Status](https://travis-ci.org/bredele/wall.png?branch=master)](https://travis-ci.org/bredele/wall)

  > Your web application foundation.

  Fast, unopinionated, minimalist and composable web framework for your [browser](#browser-support).  

```js
var wall = require('wall');
var app = wall();

app.use(auth());
app.use(localstore());
app.use('settings', settings);
```

  You probably noticed `wall` is deeply inspired by [express](https://github.com/visionmedia/express). As express, its clean and nice API provides a robust set of features to build scalable and maintainable application in a flash.

## Installation

  Install with [npm](http://nodejs.org):

    $ npm install wall

  Install with [component](http://component.io):

    $ component install bredele/wall

See [Getting started](https://github.com/bredele/wall/wiki/Getting-started).
and [API](https://github.com/bredele/wall/wiki/API-Reference).

## Philosophy

  The Wall philosophy is to reduce the complexity of your web application by splitting it into small and **self contained** modules (or apps). An app is highly extensible, configurable and communicates through event messages. 

  > Wall is inspired by [Addy Osmany](http://addyosmani.com/largescalejavascript/) and [Nicholas Zakas](http://www.slideshare.net/nzakas/scalable-javascript-application-architecture-2012) work.

  Its consistent interface makes developping a web application **as easy as playing with legos**. You can add, assemble or remove some apps, your application will never break. Most importantly, you can **[reuse](#ecosystem)** your apps in different projects and save some precious time!

  For example, a web application like Gmail would look like:

```js
var wall = require('wall');

wall()
  .use(auth())
  .use(mail())
  .use(spam())
  .use(chat()); //reused in google hangout
```

## Ecosystem

  Wall is also an ecosystem of plugins and apps. You can use apps to authenticate your apps, connect to an external service like Facebook or Twitter, store your data and way more in a single line of code. 

  See [wiki](https://github.com/bredele/wall/wiki/Plugins-and-apps) for list of third plugins and apps.

  Because Wall makes easy to expose and reuse third apps, you won't have to reinvent the wheel or do the same stuff all over again. Instead you'll be able to focus on what makes your application special.

## Features and Benefits

Features:

  - Event communication bus
  - Observable data store
  - Elegant dependencies injector
  - Lifecycle hooks
  - DOM and library agnostic
  - High test coverage
  - Support all mainstream browsers

At the opposite of many web framework, Wall doesn't make the assumption an app is related to DOM. For example, an app can just process data from a server and be used in a worker.
It does not force you to use any libray or template engine. You are free to use whatever you want and to write the code you like. 

Actually, an app could use a view plugin piped to the app hooks and events. It makes a flexible and powerful solution to create user interfaces.

```js
var ui = wall()

ui.use(view('hello', '#hello'));
ui.use(view('world', '#world'));
```

Benefits:

  - Loose coupling
  - Configurable
  - Highly extensible
  - hybrid (server side)
  - maintainable
  - reusable
  - scalable

## Contribution
I would appreciate any contribution, feedback or support:
   - If you have a related app or plugin, add it to this [list](https://github.com/bredele/wall/wiki/Plugins-and-apps)!
   - Bugs, suggestions & feature requests: [open an issue](https://github.com/bredele/wall/issues)
   - Twitter: @bredeleca
   - Github: bredele

Here's a wish list of plugins:
  - ressource (client restful services)
  - view (MVVM app)
  - web components (register or declare custom tag)
  - declarative init (init app with dom el)
  - worker (app in a worker)
  - mozilla persona (unified sign in)

## Browser Support

Store supports all mainstream browsers from IE8+.

## License

  The MIT License (MIT)

  Copyright (c) 2014 <Olivier Wietrich> Olivier Wietrich

  Permission is hereby granted, free of charge, to any person obtaining a copy
  of this software and associated documentation files (the "Software"), to deal
  in the Software without restriction, including without limitation the rights
  to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
  copies of the Software, and to permit persons to whom the Software is
  furnished to do so, subject to the following conditions:

  The above copyright notice and this permission notice shall be included in
  all copies or substantial portions of the Software.

  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
  IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
  FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
  AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
  LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
  OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
  THE SOFTWARE.
