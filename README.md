[Epicodus Cliff Notes](http://www.learnhowtoprogram.com/table-of-contents)
====================

## Table of Contents

* [HTML and CSS basics](#in-the-beginning-there-was-html-and-css)
* [JavaScript primitives, methods, and functions](#on-the-first-day-michael-created-javascript)
* [jQuery](#jquery)
* [Branching and looping in JavaScript](#branching-and-looping-in-js)
* [Debugging in Javascript](#debugging-in-javascript)
* [Behavior-driven development](#let-there-be-testing-and-there-was-testing-and-it-was-good!)
* [Command line and version control](#the-miracle-of-command-line-and-version-control)
* [Object-oriented design](#on-the-second-day-michael-created-javascript-oo)
* [Programming basics with Ruby](#on-the-third-day-michael-created-ruby)
* [Ruby syntax and TDD](#michael-said-let-there-be-more-testing)
* [OO with Ruby](#rubys-object-model)
* [Databases](#databases)
* [Database basics](#database-basics)
* [SQL basics](#sql-basics)
* [Using SQL with Ruby](#using-sql-with-ruby)
* [To do list with SQL](#to-do-list-with-sql)
* [Git](#git)
* [Join statements](#join-statements)
* [Databases with Active Record](#databases-with-active-record)
* [Inheritance and modules](#inheritance-and-modules)
* [Set up a project using Active Record](#set-up-a-project-using-active-record)
* [Bundler](#bundler)
* [Active Record validations and callbacks](#active-record-validations-and-callbacks)
* [Web applications](#web-applications)
* [Ruby on Rails with minimal magic](#ruby-on-rails-with-minimal-magic)
* [Rails setup, database, models](#rails-setup-database-models)
* [Rails routing, controllers, views](#rails-routing-controllers-views)
* [Better parameters](#better-parameters)
* [Heroku](#heroku)
* [Redirecting](#redirecting)
* [The layout](#the-layout)
* [Flash messages](#flash messages)
* [Partials](#partials)
* [Sass, the asset pipeline, and Bootstrap](#sass-the-asset-pipeline-and-bootstrap)
* [Conventional Rails](#conventional-rails)
* [Helper links](#helper-links)
* [Security basics](#security-basics)
* [Capybara](#capybara)
* [Authentication](#authentication)
* [Polymorphism](#polymorphism)
* [Paperclip](#paperclip)
* [Rails with AJAX](#rails-with-ajax)
* [Factory Girl](#factory-girl)
* [Emails](#emails)
* [Pagination](#pagination)

This document is a compilation of the [learnhowtoprogram](http://www.learnhowtoprogram.com/table-of-contents) text and cheat sheets, just in case you need a handy reference when you are out in the real world of coding. This is Jennifer McCarthy and Amy Vaillancourt-Sals's gift to all of our friends at Epicodus. Hope it helps!


##IN THE BEGINNING THERE WAS HTML and CSS

The curriculum in this section is pretty basic, so you won’t get a lot of information here.  Although, some handy resources that are mentioned are:

#####Text Editors:

  - Windows computers come with a text editor called Notepad
  - Macs come equipped with TextEdit
  - SublimeText is what we used in class! Check out this cool link for sublime text keyboard [    shortcuts](http://www.marcelkalveram.com/2013/09/10-sublime-text-shortcuts-that-every-developer-should-know/)
  - Also worth a mention is [Atom](https://atom.io/), a new text editor that is as good as Sublime and also free!

#####Helpful Links:

  - [Dropbox](http://www.dropbox.com/)
  - [Site44](http://www.site44.com/)-no longer free
  - [Brace](http://http://brace.io/)



######This is what a valid HTML document looks like:

```sh
<!DOCTYPE html>
<html>
  <head>
    <title>Example title</title>
  </head>
  <body>
    <h1>Example header</h1>

    <p>Page content</p>
  </body>
</html>
```

If the content inside a tag spans more than one line, indent everything within the tag two spaces in.  Put the closing tag on the same indentation level as the opening tag!


A reminder on how to structure anchor tags for links in HTML:

```sh
<a href="http://www.epicodus.com">I link to www.epicodus.com.</a>
<a href="another_file.html">I link to another file in the same folder as myself.</a>
<a href="anotherfolder/anotherfile.html">I link to another file in a folder called another_folder.</a>
<img src="img/ducky.png" alt="I'm an image tag for a file called ducky.png.">
```

Link a stylesheet to your HTML document:

```sh
<head>
  <link href="path/to/my/stylesheet.css" rel="stylesheet" type="text/css">
</head>
```

Don’t forget to use the JavaScript console with the shortcut Cmd+Alt+J to inspect element for use in your CSS file.

Speaking of the CSS file, more specific rules take precedence over less specific rules.  In the case of conflicting rules, the last one wins!

What’s the difference between a class and an ID?  We use the . notation to select a class and the # notation  to select an id.  You can only use an ID once on a page, and you can use a class as many times as you want.  Buy using an ID, you can be clear that you’re referring to one particular thing, rather than potentially  referring to several.

######Helpful page styling:

  - [Bootstrap](http://getbootstrap.com/)
  - [Foundation](http://foundation.zurb.com/)
  - [Skeleton](http://www.getskeleton.com/)

```sh
<link href="css/bootstrap.css" rel="stylesheet" type="text/css">
```


These styles are really great because they offer ease of use, and make you look really good at styling!  Make use of the built in grid system and responsive design they offer!

######References:

  - [Mozilla Developer Network for CSS, HTML elements, and HTML attributes](https://developer.mozilla.org/en-US/)
  - [Learn CSS Layout](http://learnlayout.com/)
  - [The HTML and CSS book](http://www.htmlandcssbook.com/)


##ON THE FIRST DAY MICHAEL CREATED JAVASCRIPT:

So, again, pretty easy stuff in this section.  Not gonna bore you with operators and simple arithmetic stuff.

Good thing to remember though, ```NaN``` and ```Infinity``` are numbers in JavaScript!

Plus, remember that a single ```=``` is the assignment operator, a triple ```===``` is a check for equality.  In JavaScript, a double ```==``` is almost never used.  It does things like return true/false for the operands, but its rules are inconsistent and hard to remember.

JavaScript has concepts called ```truthy``` and ```falsey```.  Falsey values include empty strings, the number 0, the number NaN, undefined, null and false.

######There are FIVE basic JavaScript datatypes or PRIMITIVES:
  - numbers
  - strings
  - booleans
  - undefined
  - null

Variables need to start with the key word ```var```.  In JavaScript variable names start with a lowercase letter and are written in **lower camelcase**.

Don’t forget about **variable scope**.  A variable is only available within the function in which it is defined.
Using the ```var``` keyword is what scopes your variables to the function in which they are defined. Without ```var```, your variables become global variables available anywhere.  This makes it incredibly difficult to figure out where the variable is defined to begin with.

A **method** is a message you send and the result is the response!  Methods take arguments inside the parentheses, these can be left empty, but you still always need the parentheses!

```
.toFixed()
```

Remember, an **argument** is the information you pass in to the called function, and a **parameter** is the variable that is assigned upon creating the function, which receives the argument.

```
var add = function(number1, number2) { return number1 + number2; };
add(1, 2);
```

######Resources:
  - [JSFiddle](http://jsfiddle.net/)


###jQuery

jQuery, a JavaScript library makes it easy to make web pages interactive!

Download [jQuery](http://jquery.com/download/) and choose the uncompressed, development version from the jQuery 1.x section.  Save the file into the js folder.

Make sure your script tag links to the correct version ```src =“js/jquery-1.11.1.js”```
(in this format).  Put these in the head tags of your HTML document, this is where to put information about the page that isn’t displayed.

Your own scripts.js file has to go after the jQuery file, as it will rely on jQuery functionality that must be loaded first!

The web browser loads your page from the top of your HTML document to the bottom.  Generally, it’s a good idea to wrap your JavaScript in a function passed to ```.ready()```, so that it’s executed after the page loads.

```sh
$(document).ready(function() {
  $("h1").click(function() {
    alert("This is a header.");
  });
});
```

Don’t forget, there is a handy shortcut that most developers use: instead of writing jQuery(), we can simply use ```$()```

A callback is a function passed as an argument to another function, just like in the above example.

When we use JavaScript to manipulate the page, we haven't changed the source code. No matter how much we change the page with JavaScript, if you hit the Refresh button in your browser, it will go back to the initial state. What JavaScript is doing is manipulating the **Document Object Model**, or **DOM**. The DOM is your browser's interpretation of the HTML it reads. If you inspect an element of the page, you're actually seeing the DOM, not the HTML.

When working on some tricky DOM manipulation, maybe start by selecting the element and changing its background color to green, just so that you know you have the selector working properly.

###BRANCHING AND LOOPING IN JS

**Branching** is an ```if…else``` statement

The curly braces after the if statement don't end with a semicolon. This is because an if statement isn't a statement itself; rather, it's a collection of statements. Or something like that. Just know that it's a rule: no semicolons after the curly braces for if statements.

In a branching condition, if JavaScript sees any falsey values, it will treat them as false.  Everything else is truthy.

To type multiple line statements into the JavaScript console, you can hold down ALT while you press ENTER.

**Looping** allows for DRY code.

In JavaScript you can use the newer `forEach()` method or use the more traditional method of a `for loop`.

The `for loop` takes three parameters:
  - initialization
  - condition
  - final expression

Initialize a variable, typically called index (or i for short).
The condition parameter tells the for loop when to stop running.
The final expression says to manipulate the index somehow (usually adding or subtracting 1).

####Debugging in JavaScript:

First step of debugging is to look for error messages in the console.  Once that has been flushed out, pause on exceptions.  Open the JavaScript console and switch to the tab on the top that says Sources, there's a button on the top right that looks like an octagon with a pause button. If you click it twice, it turns purple. This will cause JavaScript to stop running whenever there's an error.

Check to see what code is executed with a few `alert()`'s put strategically in your code.  Same with `console.log()`

Don’t forget about the Chrome console debugger.  This allows you to drop in and run just one line of code at a time.  Whenever Chrome JavaScript engine hits the debugger keyword, it will pause execution and let you run whatever code you want.

Read the documentation, add a background color to make sure the right thing is selected, and check the EventListeners in the Chrome DevTools.

###LET THERE BE TESTING, AND THERE WAS TESTING, AND IT WAS GOOD!   

TDD and BDD, any difference?  Nope, not really.  Just make sure you are using testing as a way to think about what you should do before doing it!
Writing tests, specifically specs within those tests, will help you design easy to understand interfaces before you get caught up in code.

Resources for JavaScript:
  - [Mocha spec framework](http://mochajs.org/) download the zip and copy mocha.js and mocha.css into spec folder
  - [Chai assertion library](http://chaijs.com/) download chai.js into spec folder

Set up a page to run your specs, usually called the `spec-runner.html` file in your spec folder


This is what your spec-helper file looks like:

```sh
<html>
<head>
  <title>Mocha spec runner</title>
  <link rel="stylesheet" href="mocha.css">
</head>
<body>
  <div id="mocha"></div>
  <script src="../js/jquery-1.11.0.js"></script>
  <script src="../js/scripts.js"></script>
  <script src="mocha.js"></script>
  <script src="chai.js"></script>
  <script>mocha.setup('bdd');</script>
  <script src="specs.js"></script>
  <script>
    should = chai.should();
    mocha.checkLeaks();
    mocha.globals(['jQuery']);
    mocha.run();
  </script>
</body>
</html>
```

###THE MIRACLE OF COMMAND LINE and VERSION CONTROL:

Welcome to [Treehouse](http://teamtreehouse.com/)!  Rumor has it that you can hold on to your Treehouse account for forever!  You may need to periodically log in and actually get some use out of it, but you should be good to go!
Treehouse has a great [Console Foundations](http://teamtreehouse.com/library/console-foundations-2) track and you should watch it if need be

P.S. Its super handy to launch SublimeText from the command line.  Do so with this command:

  ``$ ln -s “/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl”``

This will create a symbolic link to Sublime's command-line launcher that is placed in the /usr/local/bin directory, which is already in your PATH (the list of places Bash checks when you run a command). Now, you can run `$subl` to open Sublime.

[Git basics on Treehouse](http://teamtreehouse.com/library/git-basics)

Some helpful tips from Michael:

>You might notice that there are some files that are not part of your project; for example,
>Macs have hidden files in most directories called .DS_Store, and Windows directories often contain files called Thumbs.db.
>To ignore these files, create a file in your home directory called .gitignore_global. Now you'll need to add some rules of
>what types of files to ignore. Github has a great example that you can copy into your file.
>Finally, we need to tell Git to use this as a rule for all of the projects you set up on this computer:
>`git config --global core.excludesfile ~/.gitignore_global`
>Finally, to make Git use Sublime instead of vim when it needs to interact with you,
>run `$ echo "export EDITOR='subl -w'" >> ~/.bash_profile`.
>Git prefers that you add an empty line to the end of every file (it's got something to do with cross-operating system
>compatibility). Rather than having to remember to do so on every file you create, you can set up Sublime to do this for you.
>Click the Sublime Text 2 menu, Preferences, Settings - User, and then add this to the settings:
>`"ensure_newline_at_eof_on_save": true`
>Git (and most programmers) also doesn't like it when you have trailing spaces at the end of your lines. There is a preference
>to remove those in Sublime, too: `"trim_trailing_white_space_on_save": true`
>It's also very standard to use two spaces instead of tabs for indenting - different computers show tabs as taking different
>amount of room, but they all represent spaces the same way. Add these preferences in Sublime:
>`"tab_size": 2`, `"translate_tabs_to_spaces": true`


You can set your name and email for your commits in the same way we do here at Epicodus with:
```console
$ git config user.name “Your Name”
$ git config user.email your@email.com
```

##ON THE SECOND DAY MICHAEL CREATED JAVASCRIPT OO:

The most common paradigm used to organize software these days is **object oriented design**.  It uses these things called objects to organize code.  Objects do many things, but simply they store information.
`var person1 = { title: “Dr.”, lastName: “Seuss” };`
title and lastName are **properties** of the object and “Dr” and “Seuss” are called values.

You can pass objects into a function:

```sh
var people = [person1, person2,  person3];
people.forEach(function(person) {
  sayHello(person);
});
```

It's very common to have a property of an object that's an array with other objects contained within it.  To create relationships among objects, use properties whose values are arrays of other objects.

######Writing Methods:

Another primary function of objects is to add behaviors.  Objects are often said to embody state and behavior.  Properties store their state, and methods give them behavior.

JavaScript also wraps primitives (like strings and numbers) in objects.

A method is just a property whose value is a function.  To call the method we use the same notation as a property but add the () to the end so JavaScript runs the method, rather than just returning the function itself.

```sh
var rectangle = {
  length: 22,
  width: 10,
  area: function() {
    return this.length * this.width;
  }
});
```

Call this method by adding the parentheses to the end of the property:
`rectangle.area();`

Remember about scope?  So we have a method that is a property of an object, but how would we reuse that method on another object?  Maybe we should have some special type of object that automatically had the method included on it.  In JavaScript we do this by creating a **prototype**.  A prototype is an object that you can make copies of as the basis for other objects.  We can define a method on our prototype, and then whenever we need to create a new instance of the object, we can use the prototype as a starting point.

Conventionally, JavaScript developers tend to use a capital letter to start a variable name when the object is going to be used as a prototype. But actually, any object in JavaScript can be used as a prototype to create another object.

When you want to use a object as a prototype for another object, you simply pass that object into `Object.create()`. A new object is returned that has all of the same properties and methods as the original object. The new object is often called an instance of the prototype.

```sh
var Person = {
  sayHello: function() {
    alert("Hello there! I'm " + this.name + ".");
  }
};

var suzy = Object.create(Person);
suzy.name = "Suzy McSuzerson";
suzy.sayHello();

var larry = Object.create(Person);
larry.name = "Larry McLarryson";
larry.sayHello();

var lilly = Object.create(Person);
lilly.name = "Lilly McLillyson";
lilly.sayHello();
```

Call methods and properties on the instance just as if the properties were defined on the object.

Properties store information about an object; as long as the object exists, the property value is stored. Variables (including parameters) store temporary information in a function; as soon as the function finishes running, the information disappears.

##ON THE THIRD DAY MICHAEL CREATED RUBY:

Unlike JavaScript, Ruby must be installed specially on your computer.

But like JavaScript there is a handy **REPL** to practice Ruby just like the console was great for JavaScript.  This is $ irb in the console window.  IRB stands for interactive Ruby shell.
REPL stands for read, evaluate, print, loop- it reads your code, evaluates it, prints out the result, and loops back to the beginning waiting for you to type something else.

Resources:
  - [Nitrous](https://www.nitrous.io/)  gives you a virtual computer running Linux, but it uses the Bash shell that OS X does.
  - [Install Ruby](http://www.learnhowtoprogram.com/lessons/installing-ruby)  here is a link to Michael’s great steps on installing Ruby on your home machine (for a Mac)
  - [Ruby Docs](http://www.ruby-doc.org/)
  - [Rubular](http://rubular.com/)  try out regular expressions with Ruby


Some of the basics are very similar to JavaScript, so the emphasis will be on some particulars to remember.

If you put a decimal in your numbers, you’ll get a decimal back. If you don’t put a decimal, it will round down.
Numbers without decimals are called integers; numbers with decimals are called floats. JavaScript just had one type of number; Ruby has two. You have to be careful to keep the two straight.

Just like in JavaScript, you can assign numbers to a variable. But unlike JavaScript, you don't need to use the var keyword, and you don't need to end statements with semicolons. Yay!

In Ruby it is convention to use underscores to separate words in variable names, rather than capital letters.  This is called **snake_case**.
In Ruby, if a method does not take an argument, you do not need to include empty parentheses.

Remember, Ruby does not have the same type coercion that JavaScript does.  You must make sure the types are the same to use them together.

```sh
age = 5
"I am " + age.to_s + " years old."
  OR
age = 5
"I am #{age} years old."
```

Anything in the `#{}` gets evaluated by Ruby and then put into a string.  This is called **string interpolation**.
You can’t use string interpolation in single quotes!

Nil is similar to JavaScripts undefined.

In JavaScript, we used objects to represent key-value pairs, and to embody logic in our programs through creating methods on the objects. This is where Ruby and JavaScript depart greatly. Ruby has a key-value pair called a **hash**, but it's not used to embody logic the way JavaScript objects are. You can't write a method on a Ruby hash. Here's an example of a hash:

```sh
  • phones = {"Elizabeth" => 4155551212, "Robert" => 6505551212, "Christopher" => 5105551212}
  • phones["Elizabeth"]
```

The `=>` is called a hash rocket; the key is on its left, and the value is on the right.

You can’t use the dot notation like in JavaScript.

######Branching:

Branching in Ruby is similar to JavaScript, but no curly braces or parentheses.  Ruby uses `elsif` in branching statements.  Ruby doesn’t have a tripe === operator, just a double `==` operator which evaluates for equality.  There is also one more comparison keyword: `unless`.

In Ruby, everything is truthy except for false and nil.

######Looping:

`each` is similar to JavaScripts forEach(), but where in JavaScript we would pass a callback, here we pass a block.  A **block** is a lot like an anonymous function; the variable in between the pipes is like the function parameter.

Unlike in JavaScript, where the forEach() method returns undefined regardless of what happens in the callback, Ruby’s each just returns the array on which it was called.  We can use the puts method to show the output.

When you loop across a hash with each, you need to have two parameters to the block.

Remember, in JavaScript, we call a function that is called on an object a method.  In Ruby, there are no functions!  Everything is a method, even if it seems like it is not being called on anything (those are called global methods).

######Methods:

Every method begins with the keyword `def` (to “define” a method) and ends with the keyword `end`.
Method names must start with a lowercase letter.  Conventionally they are all lowercase and words are separated by an underscore in **snake_case**.

In Ruby, the last line of code that is evaluated is automatically returned from the method, no need to use the return keyword.

##MICHAEL SAID LET THERE BE MORE TESTING:

Testing in Ruby is pretty similar to testing in JavaScript.   We use the `RSpec` tool, it has very similar syntax.

Install RSpec by running `$ gem install rspec` from your terminal.

A RubyGem, or just gem, is a package that includes Ruby libraries and/or programs. Usually, they provide some kind of functionality that isn't included in the Ruby core or standard library, but that is useful in many projects and so makes sense to share.  You can make your own gem!  Follow the instructions [here](http://guides.rubygems.org/make-your-own-gem/)

To use RSpec, create a new folder for your project, another folder inside that called `lib` and another folder called `spec`.

The project file will end with a .rb extension.  The spec file should be in this format `projectfile_spec.rb`

Make sure you require ’rspec’ and require ’filename’

Your computer has a list of folders it checks when you run a command; this list is called the PATH. RSpec automatically adds the lib folder to your path, so we can just require the filename without the relative path from the spec folder.


###Ruby’s Object Model:

Objects in Ruby are totally different from objects in JavaScript.  In Ruby, EVERYTHING is an object!  For particular objects, we say it is an instance of a class.  To see what class you object belongs to you can call `.class`.  Classes start with an uppercase letter.  Ruby convention is to use **upper camel case** for class names that contain more than one word.

Even classes are objects in Ruby.  They are objects of the Class class.

To find out what methods an object has available to it, you can run the `.methods` method on it.

In JavaScript, objects are bundles of properties and their values. Some properties are methods that do some kind of work. JavaScript also has five primitive data types. Primitives also have methods and properties.

In Ruby, everything is an object. Each object has a class that tells you what type of object it is. That class contains methods that do some kind of work. There are no primitives - the Ruby equivalent of the JavaScript primitives are just objects themselves.

How to create a new object in Ruby:
  - String.new
  - Array.new
  - Hash.new

Each of these creates a new instance of that class.  Almost all classes have a new method that creates a new instance.
In JavaScript we created a new object by running Object.create() and passing in another object to use as a prototype.  In Ruby, we create a new object by calling the new method on its class.

You can create classes of your own!

```sh
class Foo
  def say_hi
    puts 'hi'
  end
end

f = Foo.new
puts f.say_hi
```

A method is defined in the class, which we then call on an **instance** of the class.

In JavaScript we’d often create an initialize() method that would do whatever we needed to set up an object.  In Ruby, the initialize method is automatically run whenever an instance of a class is created.

Just like in JavaScript, variables are scoped to the method in which they are defined, and are cleared from memory as soon as the method finishes running.  These are local variables.  Ruby has **instance variables** that include the @ symbol in front of them.

These are used when there is some property of an object that should be available to all the object’s methods.  They are a bit analogous to properties in JavaScript, except that where JavaScript properties are accessible by calling the property on the object.  Ruby instance variables are still scoped within the object that contains them.  If you want to expose them to other objects, you need to write a method for that.

```sh
class Rectangle
  def initialize(length, width)
    @length = length
    @width = width
  end

  def length
    @length
  end
end
```

Use a class method when you want to do something that involves more than one instance.  Define a **class variable** using two @@ at the beginning of the variable name.  This is like a property that’s saved on the class itself, rather than any particular instance.  Class variables can be accessed by instance methods.

When we write an instance method (in documentation, not in code), we write it like `ClassName#instance_method`; when we write a class method, we write it like `ClassName.class_method` (in both documentation and code).

New programmers often get confused about when to write a class method rather than an instance method. Here's an analogy I've found to be helpful. You can think of classes like a car factory, and instances like that cars the factory makes. Want to make a new car? That's the factory's job, so it should be a class method. Want to know what color a car is? That's about a particular car, so it should be an instance method. Want to know how many cars have been made? The factory creates the cars, so it knows how many have been made; any individual car doesn't know how many other cars have been made. Want to know how many green cars were made? Again, the factory knows about all of the cars, so it knows how many green cars were made. Want to change or destroy a car? That's about a particular car, so it should be an instance method.

Ruby can’t be used in the web browser, so Ruby code without Rails, runs in the command line.  A user interface file for a project can be run in the command line `$ ruby file_name.rb`

Don’t forget, you can rewrite your interface with [shoes.rb](http://shoesrb.com/)


Ruby has a funny thing called a symbol.
`:foo`

Symbols are used to pass data around our programs.  You can think of them as analogous to strings, but only for internal use in your program.  A string is for human readable input and outpu; a symbol is for machine readable input and output.

A common place to see a symbol is with a method called attr_reader.

```sh
class Task
  def initialize(name)
    @name = name
  end

  def name
    @name
  end
end
```

is the same as:

```sh
class Task
  attr_reader(:name)

  def initialize(name)
    @name = name
  end
end
```

attr_reader is just a special method that creates other methods in your class.  You give it a symbol, and it creates a method with the same name as that symbol, and that method returns an instance variable with the symbol name. It's just a useful shortcut so that you don't have to write methods that look so similar over and over.

It is also common to initialize an object with a hash.  The nice thing about this is that it makes it really easy to deal with optional arguments - if, for example, an attribute is optional and isn't contained in the attributes hash, Ruby will just return nil when you call attributes[attribute_name].

###Debugging in Ruby:

Ruby has a simiar set of debugging tools as JavaScript.
`puts` is much  like an alert().  `p` is a bit like console.log().  Its like puts, but when you p a single object, the output includes all of the instance variables and their values.

`binding.pry` is like debugger.  Install the pry gem and require ‘pry’ to your file; stick the call binding.pry anywhere in that file and when that point is reached, you’ll be dropped into an IRB like console.  [Check this out](http://pryrepl.org/screencasts.html)

## Databases
###Database basics
**Database relations:**

Three types of relationships:
* *One-to-many* (e.g., a course has many students, and a student belongs to one course - like Epicodus)
* *Many-to-many* (e.g., a course has many students, and a student has many courses - like college)
* *One-to-one* (a tutor who only serves a single client)

  [SQL Designer website](http://ondras.zarovi.cz/sql/demo/)

###SQL basics:
Common SQL commands:

```console
CREATE DATABASE database_name;
CREATE TABLE table_name (id serial PRIMARY KEY, some_column varchar, another_column int, yet_another_column timestamp);
ALTER TABLE table_name ADD column_name boolean;
ALTER TABLE table_name DROP column_name;
INSERT INTO contacts (name, age, birthday) VALUES ('Wes', 43, '1969-05-01') RETURNING id;
SELECT * FROM table_name WHERE age >= 18;
UPDATE contacts SET name = 'Wes Anderson' WHERE id = 1;
DELETE FROM contacts WHERE id = 1;
DROP TABLE table_name;
DROP DATABASE test_database;
```

Common psql commands:

* List all databases: `\l`
* Connect to database: `\c database_name`
* List tables in current database: `\dt`
* List columns in a table: `\d table_name`

Common column types:
```console
int
float
varchar
text (for long strings of text)
timestamp
boolean
```
Operators for WHERE clauses:
```console
=
!=
>
<
>=
<=
BETWEEN
LIKE
IN
```
###Using SQL with Ruby

Connect to a database:
```console
some_db = PG.connect({:dbname => 'some_db'})
```

Run SQL:
```console
some_db.exec("INSERT INTO contacts (name) VALUES ('michael');")
```
The results are a collection of hashes:
```console
results = address_book_db.exec("SELECT * FROM contacts;")
results.each { |result| p result }
results.each { |result| p result.class }
```
*each result is a hash*

###To do list with SQL
If you find yourself using SQL without Active Record, then go [here](http://www.learnhowtoprogram.com/lessons/to-do-list-with-sql).
Here's the link to [PostgreSQL documentation](http://www.postgresql.org/docs/9.2/static/queries-order.html)

**CRUD:** stands for Create, Read, Update, and Destroy

###Git
Getting to know Git, getting to know all about Git - check out the first two chapters. http://teamtreehouse.com/library/git-basics

Branching and merging information starts on the third chapter, appropriately called Branches.

###Join Statements
Join statement (not a join table):
```console
SELECT * FROM
animals JOIN trainers ON (animals.trainer_id = trainers.id)
WHERE trainers.id = 1;
```

3-table join
```console
select animals.* from
trainers join lessons on (trainers.id = lessons.trainer_id)
          join animals on (lessons.animal_id = animals.id)
where trainers.id = 1;
```
##Databases with Active Record
###Inheritance and modules
Find an object’s class: ex. `5.class`

When one class inherits from another, it has all of the methods available to it from the parent class. Every class inherits from `Object`. `Object` inherits from `BasicObject`. `BasicObject` inherits from *nil*.

See the methods on an object: ex. `3.methods`
Remove methods all objects have: ex. `3.methods - Object.new.methods`

Modules are collections of methods and constants that can be included in any class.

###Set up a project to use Active Record:
* Install Active Record: `$ gem install activerecord`
* Install Rake: `$ gem install rake`
* Install Active Record Migrations: `$ gem install active_record_migrations`
* Create a db folder in your project directory
* Create a file called `Rakefile` in your project directory and add this to it:
```sh
require ‘active_record_migrations’
ActiveRecordMigrations.load_tasks
```
* Create a file in db called `config.yml` and add this to it:
```sh
development:
  adapter: postgresql
  database: project_name_development
test:
  adapter: postgresql
  database: project_name_test
```
Common one-off database tasks:
* Create your test and development databases: `$ rake db:create`
* Drop your databases: `$ rake db:drop`
* Create an empty migration: `$ rake db:new_migration name=descriptive_migration_name`
* Run a migration: `$ rake db:migrate`
* Roll back a mibration: `$ rake db:rollback`
* Prepare your test database: `$ rake db:test:prepare` (might be depracated...)

**Migration Guide:**

Here’s the [Ruby on Rails guide for Active Record Migrations](http://guides.rubyonrails.org/migrations.html) - it will help remind you of what is needed to update your schema in exactly the way you want it.

And, the [Rails API documentation on migrations](http://api.rubyonrails.org/classes/ActiveRecord/Migration.html)

**Active Record queries and associations**

* [Rails Guide on querying conditions](http://guides.rubyonrails.org/active_record_querying.html#conditions)
* [Rails API documentation on query methods](http://api.rubyonrails.org/classes/ActiveRecord/QueryMethods.html)
* [Rails Guide on Active Record associations](http://guides.rubyonrails.org/association_basics.html)
* [Rails API documentation on associations](http://api.rubyonrails.org/classes/ActiveRecord/Associations/ClassMethods.html)

###Bundler
* Run `$ bundle`, when you’ve got your Gemfile all set up with the necessary gems
* Run `$ gem regenerate_binstubs`, if you get an error about using the wrong version of a gem.

###Active Record validations and callbacks

Ex. of tests for validations:
```sh
describe Task do
  it { should validate_presence_of :name }
  it { should ensure_length_of(:name).is_at_most(50) }
end
```

Ex. of how the model would look:
```sh
class Task < ActiveRecord::Base
  validates :name, :presence => true, :length => { :maximum => 50 }
end
```

Ex. of callback:
```sh
class Task < ActiveRecord::Base
  before_save :downcase_name

private

  def downcase_name
    self.name = self.name.downcase
  end
end
```
* [Rails Guide on validations](http://guides.rubyonrails.org/active_record_validations.html#exclusion)
* [Rails API documentation on validations](http://api.rubyonrails.org/classes/ActiveModel/Validations/ClassMethods.html)
* [Rails Guide on callbacks](http://guides.rubyonrails.org/active_record_callbacks.html)
* [Rails API documentation on callbacks](http://api.rubyonrails.org/classes/ActiveRecord/Callbacks.html)

###Shoulda-matchers
It’s a gem that helps to make validations, and callbacks more condensed - here’s the [documentation](https://github.com/thoughtbot/shoulda-matchers) for it.

###Polymorphic Associations
Here’s the [Rails Guide to polymorphism](http://guides.rubyonrails.org/association_basics.html#polymorphic-associations)

###Validates_timeliness
[This gem](https://github.com/adzap/validates_timeliness) is a date and time validation plugin for ActiveRecord and Rails. It supports ORMs (Object Relational Mapper) and allows custom date/time formats - it doesn’t currently support much in terms of testing.

###Textacular
[This gem](https://github.com/textacular/textacular) exposes full text search capabilities from PostgreSQL.

###Indexes for your database:
Here’s a [great article](http://robots.thoughtbot.com/a-grand-piano-for-your-violin) on the power of indexes and how it will change the way you use databases.

###Cloning a repo from Github:
Grab the link from the bottom right of the chosen Github page, and run
```console
$ git clone https://github.com/… (<- replace the url with the appropriate link)
```
To load the current schema all at once (in case there’s loads of migrations in the project), run `$ rake db:schema:load`. It’s much faster and less error prone.

**DRY:** Stands for Don’t Repeat Yourself

**Scopes:**
This is similar to the WHERE statements from back in PostgreSQL days. Here’s two examples of workable scopes:

Ex. 1 - passing through an argument:
```console
class Musician < ActiveRecord::Base
  scope :find_by_instrument, -> (instrument) { where(instrument_id: instrument.id) }
end
```

Ex. 2 - no argument to pass through:
```console
class Task < ActiveRecord::Base
  scope :completed, -> { where(completed: true) }
end
```

Here’s more information on [Scopes](http://guides.rubyonrails.org/active_record_querying.html#scopes)

##Web Applications
###Ruby on Rails with minimal magic
  **How the web works**

* **HTTP:** stands for Hypertext Transfer Protocol
* HTTP uses a client-server model, where a client sends a request, and a server provides a response. Web browsers are clients.
* A request includes a method (also called a verb), a path, headers, and a body.
* Methods indicate the the type of action.
* The path is the URL, like:
`http://www.epicodus.com/students.html`.
* Headers include optional information, like format or authentication.
* The body includes information like the contents of a form.

**Common HTTP methods:**
* **GET** retrieves information without changing anything on the server.
* **POST** creates something.
* **PATCH** or **PUT** updates.
* **DELETE** destroys.

Responses include status, headers, and body. The status is a three-digit code that represents the outcome of the request. Headers might include content type or redirect location. The body includes the actual HTML, CSS, JavaScript, etc.

**Common statuses:**
```console
200 OK (successful)
201 Created
301 Moved Permanently
302 Moved Temporarily
400 Bad Request
403 Forbidden (it exists but you aren't allowed to see it)
404 Not Found
422 Unprocessable Entity (you put in bad data)
500 Internal Server Error
502 Bad Gateway (the server sent the request to another server and got an invalid response)
503 Service Unavailable (the server is overloaded or down for maintenance)
```
###Rails setup, database, models
* Rails uses the model-view-controller pattern:
* The router parses the request and passes it to a controller.
* Controllers tell the model to do some work and then render a view.
* Models embody the application logic, and can be plain Ruby objects or inherit from Active Record.
* Views are HTML with some Ruby sprinkled in.
* Create a file called '.railsrc' in your home directory and type `-d postgresql -T`.
* Make a new Rails app: `$ rails new your_app_name`
* Example of what your config/database.yml might look like:

```sh
development:
   adapter: postgresql
    database: wikipages_development
test:
    adapter: postgresql
    database: wikipages_test
```
* To create a new migrations, run: `$ rails g migration your_migration_name`
* To Set up RSpec, run: `$ rails generate rspec:install`
* To get an IRB shell with the Rails development environment loaded, including gems and models, run: `$ rails console`

**Comprehensive Gemfile Example** (please remember to look up gems if you don’t know what they do):

```sh
source 'https://rubygems.org'

gem 'rails'
gem 'pg'
gem 'sass-rails'
gem 'uglifier'
gem 'coffee-rails'
gem 'jquery-rails'
gem 'turbolinks'
gem 'jquery-turbolinks'
gem 'bcrypt', '~> 3.1.5'
gem 'bootstrap-sass', '~> 3.2.0'
gem 'autoprefixer-rails'
gem 'devise'
gem 'simple_form'

group :development do
    gem 'better_errors'
    gem 'binding_of_caller'
    gem 'quiet_assets'
end

group :test, :development do
    gem 'rspec-rails'
    gem 'pry'
    gem 'launchy'
    gem 'rest_client'
    gem 'dotenv-rails'
end

group :test do
    gem 'shoulda-matchers'
    gem 'factory_girl_rails'
    gem 'capybara'
    gem 'webmock'
end

group :production do
    gem 'rails_12factor'
end
```
###Rails routing, controllers, views
* To start the local Rails server, run: `$ rails server`, or `$ rails s`
* View your app at http://localhost:3000

**7 RESTful actions** (stands for Representational State Transfer):
```console
GET (index)
GET (new)
POST (create)
GET (show)
GET (edit)
PUT/PATCH (update)
DELETE (destroy)
```
Your RESTful actions will live in your controllers. If you feel the need to create another method, your model is a good place for that!

What 'resources :contacts' does in your 'routes.rb' file:
```sh
Wikipages::Application.routes.draw do
    match('contacts', {:via => :get, :to => 'contacts#index'})
    match('contacts/new', {:via => :get, :to => 'contacts#new'})
    match('contacts', {:via => :post, :to => 'contacts#create'})
    match('contacts/:id', {:via => :get, :to => 'contacts#show'})
    match('contacts/:id/edit', {:via => :get, :to => 'contacts#edit'})
    match('contacts/:id', {:via => [:patch, :put], :to => 'contacts#update'})
    match('contacts/:id', {:via => :delete, :to => 'contacts#destroy'})
end
```
###Better parameters
Changing this,:
```sh
@contact = Contact.new( :name => params[:name],
                        :phone => params[:phone],
                        :email => params[:email])
```
to this:
```sh
    def new
        @contact = Contact.new(contact_params)
    end

private
    def contact_params
        params.require(:contact).permit(:name, :phone, :email)
    end
end
```
###Heroku
Watch the [screencast](https://www.codeschool.com/code_tv/heroku) on how to put your Rails sites online.

Make sure heroku-toolbelt is installed
```console
$ brew install heroku-toolbelt (if your on a Mac)
```

Make sure your Gemfile includes the `gem 'rails_12factor'` in your :production group.

When starting on a new computer, generate a new pair of SSH keys:
```console
$ ssh-keygen -t rsa -C your_email@address.com
```
Run:
```console
$ heroku login
$ heroku keys:add
```
**Set up your Heroku app**

If you haven’t created a Heroku app yet, run: `$ heroku create your_app_name`

If you’ve already created a Heroku app, run: `$ heroku git:remote -a your_app_name`

Push your code to Heroku with: `$ git push heroku master`

To migrate your database, run: `$ heroku run rake db:migrate`

If you want to add a team member:

`$ heroku sharing:add your_friends_email#their_address.com`

If you get the error `Permission denied (publickey)`, run `$ rm ~/.ssh/*` to clear the SSH settings off the machine, then start the process again with adding a new pair of SSH keys.

###Redirecting
`redirect_to:`
should be used after a successful create, update, and destroy. It takes a URL as its argument and causes the browser to make an entirely new request.

`render:`
should be used after unsuccessful creates and updates, so that the problematic information can be displayed on the screen to be fixed. It takes a view as an argument and simply returns HTML as a response to the current request.

###The layout
If you want to have every page list a different title, add this to your `app/views/layouts/application.html.erb` file:
```sh
<title><%= yield(:title) %></title>
```
On your other view pages, add something like this:
```sh
<% content_for(:title, "New contact | Wikipages") %>
```
If your wanting your navbar to change depending on the view, try this:
```sh
<% content_for(:navbar) do %>
    <li><a href="/">Home</a></li>
    <li><a href="something/else">Something else</a></li>
    <li><a href="etc">Etc.</a></li>
<% end %>
```
###Flash messages
You can add flash messages to your controller methods, like this:
```sh
class ContactsController < ApplicationController
    def create
        @contact = Contact.new(params[:contact])
        if @contact.save
            flash[:notice] = "Your contact was added to Wikipages."
            redirect_to("/contacts/#{@contact.id}")
        else
            render('contacts/new.html.erb')
        end
    end
end
```
Just remember to add this to your app/views/layouts/application.html.erb file, in the <body>:
```sh
<%= flash[:alert] %>
<%= flash[:notice] %>
```
###Partials
Partials allow you to render chunks of code that you would otherwise be repeating.

Here’s the errors partial we’ve been using (make a file `_errors.html.erb` in your `view/layouts folder`):
```sh
<% if object.errors.any? %>
      <h3>Please fix these errors:</h3>
      <ul>
      <% object.errors.full_messages.each do |message| %>
         <li><%= message %></li>
      <% end %>
      </ul>
<% end %>
```
This is how you would render the _errors.html.erb partial on your views page:
```sh
<%= render('layouts/errors', :object => @contact) %>
```

###Sass, the asset pipeline, and Bootstrap
Michael’s reference for this is more comprehensive than I can make cliff notes for, so here’s the [link that that page](http://www.learnhowtoprogram.com/lessons/sass-the-asset-pipeline-and-bootstrap), for quick look-up

##Conventional Rails
###Magic methods
This is where we changed our routes from `match` to `resources`. Here’s an example of what that looks like (`config/routes.rb`):
```sh
Wikipages::Application.routes.draw do
    resources :contacts do
        resources :phones, :only => [:new, :create]
    end

    resources :phones, :except => [:new, :create]
end
```
To see your routes, run: `$ rake routes`

You can now use the route paths in your controller, here’s an example of that:
```sh
def create
    @contact = Contact.new(params[:contact])
    if @contact.save
        flash[:notice] = "Contact created."
        redirect_to contacts_path
    else
        render 'new'
    end
end
```
###Helper links
Writing links with helpers:
```sh
<%= link_to "New contact", new_contact_path, :class=> "btn btn-default" %>
Deleting with helper links:
<p><%= link_to "Delete", contact_path(@contact),
                         :data => {:confirm => "You sure?",
                                   :method => "delete"},
                         :class => "btn btn-danger" %></p>
```
Writing forms with helpers:
```sh
<%= form_for(@contact) do |f| %>
      <div class="form-group">
          <%= f.label :name %>
          <%= f.text_field :name %>
      </div>
     <div class="form-group">
          <%= f.label :phone %>
          <%= f.text_field :phone %>
     </div>
      <div class="form-group">
         <%= f.label :email %>
          <%= f.text_field :email %>
     </div>
      <%= f.submit(:class => "btn btn-primary") %>
<% end %>
```
###Security basics

**CSRF:** stands for Cross-Site Request Forgery. Here's how CSRF works:

* You log into your bank account at www.yourbank.com and a cookie is placed on your computer to identify you.
* You don't log out, and then you visit a chat board. The cookie remains on your computer.
* On the chat board, a malicious user could then write some code to nab your cookie and wreak havoc with your bank account.

To keep this from happening, Rails creates an autenticity token. `form_for` automatically adds tokens to your forms. HTML forms should include something like this:
```sh
<input name="authenticity_token" type="hidden" value="c6j4CiHdGCJ5NcjWXvEQXGIsjCbrKQ4zpJYcyhCWn9E=" />
```
Also, make sure that `protect_form_forgery with: :exception` is turned on in your `ApplicationController`.

**Mass assignment**

* Check out [Treehouse’s blog on Strong Parameters](http://blog.teamtreehouse.com/rails-4-strong-paremeters)
* There’s a [RailsCast video on this too](http://railscasts.com/episodes/26-hackers-love-mass-assignment-revised) if you have access to an account.

**SQL injection**
* [Read all about it!](http://guides.rubyonrails.org/security.html#sql-injection)

**Ruby drop-down menu code**

* Ex. `<%= f.collection_select :station_id, Station.all, :id, :name %>`

**Ruby checkboxes**
* Here’s the [documentation](http://edgeapi.rubyonrails.org/classes/ActionView/Helpers/FormBuilder.html#method-i-collection_check_boxes)

###Capybara
This is a testing tool, similar to mocha and chai, that allows a developer to test the flow of their application. Here’s how you can get started with Capybara:

* Install ‘capybara’ in your Gemfile
* `require ‘capybara’` in your rails_helper
* Create a “features” folder in your spec folder

Here’s the documentation on Capybara:
[Capybara README](https://github.com/jnicklas/capybara)
[Using Capybara with RSPEC](https://github.com/jnicklas/capybara#using-capybara-with-rspec)

Remember to use the [launch gem](https://github.com/copiousfreetime/launchy) to make debugging in Capybara a happier time.

###Authentication
You can create a user authentication from scratch, if you like. There’s a [RailsCast video](http://railscasts.com/episodes/250-authentication-from-scratch-revised) on this, if you have access to it.

Otherwise, you can create user authentication using the [Devise gem](https://github.com/plataformatec/devise/).

Here’s how you would go about doing that:
```console
$ rails g devise:install
$ rails g devise user
$ rake db:migrate
$ rails g devise:views
```
Add `gem 'devise'` to your Gemfile. Don’t forget to run `$ bundle` and restart your server.

Add this to your `config/environments/development.rb` file:
```sh
config.action_mailer.default_url_options = { :host => 'localhost:3000' }
```
Here’s a good example of the links to sign in paths, to be added onto your
`layouts/application.html.erb` file (either directly on the file or through a partial):
```sh
<% if user_signed_in? %>
  Logged in as <strong><%= current_user.email %></strong>
    <%= link_to 'Edit profile', edit_user_registration_path %> |
    <%= link_to "Logout", destroy_user_session_path, method: :delete %>
<% else %>
    <%= link_to "Sign up", new_user_registration_path %> |
    <%= link_to "Login", new_user_session_path %>
<% end %>
```
Make sure your `config/routes.rb` looks something like this:
```sh
devise_for :users, path_names: {sign_in: "login", sign_out: "logout"}
```
Add something similar like this to your class controller pages:
```sh
before_filter :authenticate_user!, except: [:index, :show]
```
###Polymorphism
This is in reference to the whole commenting on comments thang in the Hacker News clone project. Here’s the [documentation on polymorphic associations](http://guides.rubyonrails.org/association_basics.html#polymorphic-associations)

Your associations will look something like this:
```sh
class Comment < ActiveRecord::Base
    belongs_to :commentable, :polymorphic => true
    has_many :comments, :as => :commentable
end

class Link < ActiveRecord::Base
    has_many :comments, :as => :commentable
end
```
###Paperclip
This is a [popular gem](https://github.com/thoughtbot/paperclip) for handling uploaded files to your app.

If you are using Heroku to host your Paperclip app, be sure to look over [here](https://devcenter.heroku.com/articles/paperclip-s3) and [here](https://devcenter.heroku.com/articles/config-vars).


##Rails with AJAX
###Getting started with AJAX
I think the important thing to know about AJAX is that it’s a way of using javascript and jQuery to render partials rather than reloading the whole page, or loading a new view entirely. Here’s some resources that will hopefully help you along the way:

* [Treehouse on AJAX](http://teamtreehouse.com/library/ajax-basics/ajax-concepts/introducing-ajax)
* [RailsCast on AJAX](http://railscasts.com/episodes/136-jquery-ajax-revised)
* [A YouTube video on AJAX](https://www.youtube.com/watch?v=n6eE-nd3ci4)

If you’d like to use Capybara testing with AJAX, be sure to check out [PhantomJS](http://phantomjs.org/) and [Poltergeist](https://github.com/teampoltergeist/poltergeist)

[DatabaseCleaner](https://github.com/DatabaseCleaner/database_cleaner#rspec-example) is effective with overcoming the problem with threading and database transactions.

###Factory Girl
[Factory Girl](https://github.com/thoughtbot/factory_girl_rails) is a library for setting up Ruby objects as test data. In otherwords, if you’d like to create a user object so you don’t have to repeat yourself in your tests, this tool is for you! (Helpful for creating other objects too - it’s not limited to just creating a user).


To install:

* Run: `$ gem install factory_girl`
* Add to your Gemfile: `gem ‘factory_girl_rails”`
* Run: `$ bundle install`
* Remember to restart your server
* Create a file called `factories.rb` in your spec folder

Here’s an example of how you might use Factory Girl:
```sh
FactoryGirl.define do
  factory(:user) do
    username('Jane')
    email('Jane@doe.com')
    password('password123')
    password_confirmation('password123')
  end
end
```

If you have authentication on your users, this will help you create a test users with minimal snags:
```sh
FactoryGirl.define do
  factory :user do |user|
    sequence(:email) { |n| "user#{n}@factory.com" }
    user.password{ "supersecretpassword" }
  end
end
```

###Emails
Rails has a built-in system for sending emails called Action Mailer. Here’s the [Railscast video](http://railscasts.com/episodes/61-sending-email-revised) on the subject.

You can use the [letter_opener gem](https://github.com/ryanb/letter_opener) to see the emails pop up on a web page.

To send actual emails, [Mailgun](http://www.mailgun.com/) was recommended to us. Here’s [Heroku instructions](https://devcenter.heroku.com/articles/mailgun) for setting up Mailgun.

Here’s a [helpful blog post](http://www.robbyonrails.com/articles/2009/11/16/sending-email-controllers-versus-models) on the subject of sending emails from the Model, rather than the Controller (a better practice).

###Pagination
Kaminari is a recommended paginator for Rails 3 and 4 - check it out:
https://github.com/amatsuda/kaminari
