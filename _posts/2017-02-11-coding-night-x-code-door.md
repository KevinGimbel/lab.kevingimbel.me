---
layout: post
title:  "Coding Night x CodeDoor"
date:   2017-02-11 23:14:51 +0100
categories: workshop
---

Welcome to the Coding Night x CodeDoor Workshop "Creating a website with GitHub
and Jekyll". In this workshop you will get an overview of HTML and CSS, git and
GitHub and Jekyll, a static site generator. This lab website is made with Jekyll
as well.

## Lab 1: Installing git

[Git](https://git-scm.com) is a version control system used by software
developers to control their code an work together. It allows us to collaborate
and share code, make changes to files and bring together these changes. If you
have any questions during this lab feel free to ask!

### Install git

To install git go to
[https://git-scm.com/downloads](https://git-scm.com/downloads) and chose your
operation system: MacOS, Linux, or Windows and follow the instructions. If you
have any issues, aks me to help you!

#### Alternative ways to install git

**Mac OS**
On Mac OS, you can use `brew` to instal git. [brew](https://brew.sh) is a
package manager for Mac applications and software which is widely used. If you
have not yet installed it and want to try it out do so! If you have it installed
and want to know more feel free to ask me.

**Linux (Ubuntu)**
On Ubuntu `git` is available under `apt`, the package manager for Ubuntu. It can
be installed by running the following commands inside a terminal:

```sh
$ sudo apt-get update
$ sudo apt-get install git
```
*Note: You don't type the `$`- it's just the prompt`*

### Verify git is installed
Once git is installed, verify it is working by running the `git --version`
command inside a terminal. The output should look smiliar to

```sh
git version 2.11.0
```
*Note: If your version is higher or lower do not panic! It's okay to run a
slightly older or newer version for this workshop.*

### Creating your first git repository

Create a new folder on your computer and go inside - this can be done from the
terminal.

**Mac OS and Linux**

```sh
$ cd $HOME
$ mkdir codingnight
$ cd codingnight
```

**Windows**

```sh
C:\> cd %HOMEPATH%
C:\> mkdir codingnight
C:\> cd codingnight
```

You now have created a new folder called `codingnight` inside your users home
directory. We will use this folder to write all code for this tutorial.

**Make the new folder a git repository**

So far the new folder is just a simple folder. To make it a git repository we
need to initialize a git repository inside the folder with `git init`.

Open your terminal again and run the following commands to create the git
repository.

**Max OS, Linux and Windows**

```sh
$ git init
```

The output you see is similar to the following

```sh
$ git init
Initialized empty Git repository in /Users/kevingimbel/codingnight/.git/
```
*Note: The path at the end will look different for you.*

Inside your `codingnight` folder is now a `.git` folder. This is a so called
[hidden folder](https://en.wikipedia.org/wiki/Hidden_file_and_hidden_directory) because it starts with a dot (`.`). Hidden folders are not visible by default and hold configuration files. You can see hidden folders from the terminal with the following commands.

**Max OS and Linux**
```sh
$ ls -ahl
```

**Windows**
```sh
$ dir /ah
```

Inside this hidden folder git stores meta files. These files describe the
repository and stores the remotes. Remotes are references to a server where the
code is stored, for example on [GitHub.com](https://github.com).

We will now create a `README.md` file. This file is used to describe your code
and helps other people understand it better when they view the repository on
GitHub.

Open your text editor (`Atom`, `vim`, `Sublime Text`, etc.) and create a file
named `README.md`. Inside this file, write the following.

```md
# codingnight workshop

Welcome to my example HTML and CSS repository. Inside the repository you will
find some HTML and CSS code created during the Workshop.
```

What's written inside is `Markdown`. Markdown is a language that can be compiled
to HTML. It's a standard for writing documents in a abstract and simple way. You
can find out more in the [markdown
documentation](https://daringfireball.net/projects/markdown/syntax). Some
Markdown examples can be seen below. On the left is markdown, on the right the
HTML it creates. We will cover markdown more in-depth later!

```
  Markdown                HTML
  # Test              <h1>Test</h1>
  ## Test             <h2>Test</h2>
  ### Test            <h3>Test</h3>

[test](/test/)    <a href="/test/">Test</a>

> A quote         <blockquote>A quote</blockquote>
```

Markdown looks complicated at first but once you get to know it you will see
it's easy and fast to write in!

Now we will create a repository on GitHub and publish our code.

### Creating a repository on GitHub

Login to your GitHub account ot create a new one. After you are logged in, open
your profile and create a new repository by clicking on the "New" Button as
seen in the image below.

!["GitHub profile page"](/assets/img/github_new_repo.png)

You will see a screen where GitHub wants you to fill in some fields. Enter the
repository name, for example `codingnight-workshop` and a description if you want.
Click on "Create repository" to finish the setup.

!["GitHub repository information screen"](/assets/img/github_new_repo_meta.png)

Now you see some information on how to publish code to the new repository. We
want to use the second option under "...or push an existing repo from the
command line".

!["GitHub information about remotes"](/assets/img/github_new_repo_remotes.png)

Copy the line starting with `git remote add` into your terminal and hit `Enter`.
This will add the GitHub URL as remote repository so we can publish our code to
it.

### Add your code

We have created a git repository on our computer and a git repository on
GitHub.com so far, now we need to `add` our code (the `README.md` file) and
publish it - or `push` how git names it.

Run the following inside your terminal.

```sh
$ git add .
```

`git add .` adds all the changes to the current `commit`. A commit is a set of
new, deleted, or modified files. Each commit represents a fixed point in "time"
for the repository. This way we can go back to a previous version of the code at
any time. The `.` in `git add` means "add all changes". If you want you can
also a single file with `git add filename`, e.g. `git add README.md`.

Next we need to create a commit. A commit is like a "change set" which
represents one or more file changes to our code. Each commit needs a message and
is assigned an ID. To create a commit, run the following.

```sh
$ git commit -m "My first commit"
```

`My first commit` is the commit message. This is visible inside the git history
and on GitHub. This way you can tell your co-workers what changes you did to the
files.

Now that all is added we can push our code to GitHub. To do so, run
`git push origin maste`.

```sh
$ git push origin master
```
*Note: `origin` is the name of the remote added with `git remote add
origin`.`master` is the name of the branch. You can have multiple branches.*

If you open GitHub again you will see your newly setup repo!

!["A brand new GitHub Repository"](/assets/img/github_new_repo_finished.png)

This is the end of Lab 1. If you still have time left, feel free to read through
[Getting Started with
git](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) or add more files to your repository.

### Recap

To publish our code on GitHub, we need to create one repository on our computer
with `git init` and one on GitHub.

We can add changes with `git add`. With `git status` we can see new, deleted,
changed, or modified files.

With `git commit -m ""` we create a new commit which is like a set of file
changes. This commit needs a message (`-m ""`). The message can be seen on
GitHub.com and inside the git history.

To publish our changes to the remote repository, we must run `git push origin
master`. `git push` is the command, `origin` is the name of the remote url, and
`master` is the branch name.

## Lab 2: HTML

HTML (Hyper Text Markup Language) is the language of the web. All websites
are HTML when they are displayed inside the browser. You can write HTML by hand
or use different programming langauge to create it. For this Lab we will start
by writing it from hand to get familiar with HTML.

Create a new folder called `html` inside your `codingnight` folder. Inside this
folder, create a file called `index.html`. This file contains our HTML code.
Write or copy the following HTML into the file.

```html
<!DOCTYPE html>
<html>
<head>
  <title>My first HTML website</title>
</head>
<body>
</body>
</html>
```

These 8 lines of code are a empty html page with a title. You can open the file
in your browser to see how the browser will display it. To open the file,
right-click it and choose "Open in Chrome" (or "Open in Firefox"). You will see a white
page and the title "My first HTML website".

### Adding  content

Everything visible inside the browser must be between `<body>`and `</body>`. For
this lab you will write your name as a headline (`<h1></h1>`) and a bit of text
about yourself: Your hobbies, your favorite movie, your favorite music -
whatever you like. If you are not sure which HTML tags to use, feel free to ask
or look at the table below as well as some code examples.

| HTML | Description |
|----------|-------------|
| `<head>` | Inside `head` all meta information is stored. For example the `title` of your website |
| `<body>` | The `body` holds all your content and everything visible inside the browser |
| `<h1>` | To create a headline use `<h1>`. Headlines are displayed in a bigger font. There are 6 types of headlines, `h1`, `h2`, `h3`, `h4`, `h5;` and `h6`. `h1` is the biggest and most important, `h6` is the smallest. |
| `p` | A paragraph is a block of text. Multiple lines of text are wrapped in `<p>`and `</p>` |
| `ul` | With `ul` an unordered list is created. This list has points instead of number for each element on the list |
| `li` | A list item (`li`) is placed between `<ul>` and `</ul>`. It contains text that is displayed as list |

**A HTML To-Do List**

This code:

```html
<ul>
  <li>Learn HTML</li>
  <li>Learn some Markdown</li>
  <li>Create a GitHub account</li>
</ul>
```

Becomes:
* Learn HTML
* Learn some Markdown
* Create a GitHub account


The code inside your body should look something like this.

```html
<h1>Kevin Gimbel</h1>
<p>I am a software developer who likes to go to concerts. Punk
and Electronic music is my favorite - as long as
it has a lot energy!</p>
<p>I also like to play video games, especially Elder Scrolls and Fallout games.</p>
```

If it looks different that's okay - it's your first website! Add your changes and push them to GitHub. If you don't remember how, look at the previous exercise.

## Lab 3: CSS

> For this Lab some example code is available on [CodePen](http://codepen.io). CodePen is a free-to-use online code editor for HTML, CSS and JavaScript.

CSS, _Cascading Style Sheets_, is the styling language of the web. It defines what color a text has or how big a `<div>` should be. CSS is an important part of working with websites. Learning CSS is relatively easy - mastering it is hard. In this Lab you will learn about applying styles to different parts of our website and how CSS files are included into a website.

The CSS Syntax consists of 3 parts: The *selector*, and one or more *`property: value;`* pairs. The selector references a HTML element inside your website. This can be done with a class name (`.my-class`, `.content`), an element name (`div`, `p`) or an ID (`#myid`, `#content`). It is good practice to not use IDs, so we will only use class names and element names during this course. A class name always starts with a `.` (dot) followed by a word. A numeric value is not allowed, so `.63` is not a class name.

The selector `.headline` matches all HTML elements with an Attribute `class="headline"`. The selector `p` matches all `p` tags. Following this schema we can combine HTML and CSS to style our website as we wish. The below CSS code will turn all `.headline` elements red and makes them use the `font-size` of `42px`.

```css
.headline {
  color: red;
  font-size: 42px;
}
```

CSS can be placed inside a file with the file extension `css`, `style.css` for example. It can also be placed inside the `<head>` of a website. For our first example, we will place it inside the `<head>`.

### Create a new test page

Create a new folder called `css` inside the `codingnight` folder. Inside the `css` folder, create an `index.html` file with the code below.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Working with CSS</title>
    <style type="text/css">
      /* Add your CSS code below. */
    </style>
  </head>
  <body>
    <div class="content">
      <h1>Learning CSS</h1>
      <h2>Styling websites</h2>
      <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
    </div>
  </body>
</html>
```

Next, write some CSS so the following conditions are met:

- The whole website should use the `Arial` `font-family`
- The `.content` has the background color `#ddeeaa`
- The `.content` has a `padding` of `10px` on all sites
- The headline, _"Learning CSS"_, uses a `font-size` of `32px`
- The second headline, _"Styling websites"_, has a `#acc` background and `5px` `padding`

Got stuck? Fell free to ask questions or read throught the previous sections. You can also use the web and search, on [google](https://google.com), for example. Maybe a search for _"CSS set font size"_ can help you! Programming is all about learning and researching things. When you are done, look at this [example on CodePen](http://codepen.io/kevingimbel/pen/pRGJBX) - your site should look similar.

You just learned how to apply styles to HTMl elements. Now change the HTML by adding a second paragraph (`<p>`) with some Lorem Ipsum text inside. Lorem Ipsum is a simple dummy text used for prototyping designs or websites.

```html
<p>"Lorem ipsum" is just a dummy text.</p>
```

Add this new `<p>` tag below the first paragraph and assign it the class `footnote`. Now add CSS to make the `p` tag with the class `footnote` display smaller text, let's say 12px.

Next make the `p` tag display in `font-weight` bold with the following CSS. Did you notice something?

```css
p {
  font-weight: bold;
}
```

When you wrote the above CSS code, the `footnote` also got the `font-weight: bold` style. Why? Because of the `C` in CSS - the Cascading. Cascading means styles "fall down".  The `<p class="footnote">` element gets its styles from both a class (`.footnote`) and the element selector (`p`). To prevent this, we can add another class to the `<p>` element prevent this or wrap the first `<p>` tag inside another `<div>` as shown below. There are always multiple ways to solve an issue - it's up to you to find the one that fits you best.

```html
<div class="content">
  <h1>Learning CSS</h1>
  <h2>Styling websites</h2>
  <div class="intro">
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
  </div>
  <p class="footnote">"Lorem ipsum" is just a dummy text.</p>
</div>
```

Now, change the `p` selector to `.intro` - the CSS is now only applied to the long text. The code is [available on CodePen](http://codepen.io/kevingimbel/pen/GrzoWg).
