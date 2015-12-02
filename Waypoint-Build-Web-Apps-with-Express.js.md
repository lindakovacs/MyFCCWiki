# Author
![@Rafase282](https://avatars0.githubusercontent.com/Rafase282?&s=128)

Submitted by Rafase282

[Github](https://github.com/Rafase282) | [FreeCodeCamp](http://www.freecodecamp.com/rafase282) | [CodePen](http://codepen.io/Rafase282/) | [LinkedIn](https://www.linkedin.com/in/rafase282) | [Blog/Site](https://rafase282.wordpress.com/) | [E-Mail](mailto:rafase282@gmail.com)

# Build Web Apps with Express.js
# Hello World!
Create an Express.js app that outputs "Hello World!" when somebody goes to /home.

The port number will be provided to you by expressworks as the first argument of the application, ie. process.argv[2].

## HINTS
This is how we can create an Express.js app on port 3000, that responds with a string on '/':

```
var express = require('express')
var app = express()
app.get('/', function(req, res) {
  res.end('Hello World!')
})
app.listen(3000)
```

Please use process.argv[2] instead of a fixed port number:

```
app.listen(process.argv[2])
```

## My Solution

```js
var express = require('express')
var app = express()
app.get('/home', function(req, res) {
  res.end('Hello World!')
})
app.listen(process.argv[2])
```

It is similar to node which in turn is similar to JavaScript so everything is easier to pickup.

# Static
Apply static middleware to serve index.html file without any routes.

Your solution must listen on the port number supplied by process.argv[2].

The index.html file is provided and usable via the path supplied by process.argv[3]. However, you can use your own file with this content:

```html
    <html>
      <head>
        <title>expressworks</title>
        <link rel="stylesheet" type="text/css" href="/main.css"/>
      </head>
      <body>
        <p>I am red!</p>
      </body>
    </html>
```

## HINTS
This is how you can call static middleware:

```
app.use(express.static(path.join(__dirname, 'public')));
```

For this exercise expressworks will pass you the path:

```
app.use(express.static(process.argv[3]||path.join(__dirname, 'public')));
```

## My Solution

```js
var express = require('express')
var path = require("path")
var app = express()
app.use(express.static(process.argv[3]));
app.listen(process.argv[2])
```

Official Solution:

```js
var path = require('path')
    var express = require('express')
    var app = express()

    app.use(express.static(process.argv[3]||path.join(__dirname, 'public')));

    app.listen(process.argv[2])
```

# Jade
Create an Express.js app with a home page rendered by Jade template engine.

The homepage should respond to /home.

The view should show the current date using toDateString.

## HINTS
The Jade template file index.jade is already provided:

```
h1 Hello World
p Today is #{date}.
```

This is how to specify path in a typical Express.js app when the folder is 'templates':

```
app.set('views', path.join(__dirname, 'templates'))
```

However, to use our index.jade, the path to index.jade will be provided as process.argv[3].  You are welcome to use your own jade file!

To tell Express.js app what template engine to use, apply this line to the Express.js configuration:

```
app.set('view engine', 'jade')
```

Instead of Hello World's res.end(), the res.render() function accepts a template name and presenter data:

```
res.render('index', {date: new Date().toDateString()})
```

We use `toDateString()` to simply return the date in a human-readable format without the time.

## My Solution
You will need to install jade first: `npm install jade`

```js
var express = require('express')
    var app = express()
    app.set('view engine', 'jade')
    app.set('views', process.argv[3])
    app.get('/home', function(req, res) {
      res.render('index', {date: new Date().toDateString()})
    })
    app.listen(process.argv[2])
```

# Good Old Form
## My Solution
# Stylish CSS
## My Solution
# Param Pam Pam
## My Solution
# What's In Query
## My Solution
# JSON Me
## My Solution