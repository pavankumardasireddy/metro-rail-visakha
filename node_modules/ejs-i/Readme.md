# EJS-i [![npm version](https://badge.fury.io/js/ejs-i.svg)](http://badge.fury.io/js/ejs-i) [![build status](http://img.shields.io/travis/badges/shields.svg)](https://travis-ci.org/michaelerobertsjr/ejs-i)

Embedded JavaScript templates with include variable.

## Installation

    $ npm install ejs-i

## What it does

* Adds the ability to use more dynamic (variable) includes. This module  
contains all the standard features of ejs plus the ability to include variable names 
as well as the standard ejs `include fileName` feature.

## Using include variableName

First, you must pass the variable with the renderer for your variable to be 
accessible on the page where you are calling the include function.
    
    // eg. you can build strings that contain a filename
    var page = 'dynamicPageName.ejs';
    
    // eg. you can use nested objects as well
    var options = {
        filename: file,
        cache: true,
        files: {
            header: '../path/to/header.ejs',
            body: page, 
            footer: '../path/to/footer.ejs'
            }
        };
    };

    ...

    ejs.render(string, options) 

Then, on template page(s) you can use:

    <% include files.header %>
    <% include files.body %>
    <% include files.footer %>

as well as the standard ejs includes:

    <% include header.ejs %>

## ejs-i Includes All Standard EJS Features

This is a fork of ejs, so all the standard library features are supported.

The main documentation for ejs is here [ejs](https://github.com/tj/ejs) 

## Additional Features / Support

More features are planned, as well as tests.  If you have any issues please
submit them via Github. If you would like to see additional feature 
implemented, please fork and submit a pull request. Please include tests 
with your pull request.

## License 

(The MIT License)

ejs copyright (c) 2009-2009 TJ Holowaychuk &lt;tj@vision-media.ca&gt;

ejs-i copyright (c) 2015 Michael E Roberts Jr &lt;michael.e.roberts.jr@gmail.com&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
