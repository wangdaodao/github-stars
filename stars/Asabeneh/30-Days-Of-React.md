---
project: 30-Days-Of-React
stars: 26898
description: 30 Days of  React challenge is a step by step guide to learn React in 30 days.  These videos may help too: https://www.youtube.com/channel/UC7PNRuno1rzYPb1xLa4yktw
url: https://github.com/Asabeneh/30-Days-Of-React
---

30 Days Of React
================

**Learn with Asabeneh by joining the upcoming _CODING BOOTCAMP_**

Author: Asabeneh Yetayeh  
October, 2020

Day 1 >>

\# Day

Topics

00

Introduction  
How to Use Repo  
Requirements  
Setup

01

JavaScript Refresher

02

Getting Started React

03

Setting Up

04

Components

05

Props

06

List, Map and Keys

07

Class Components

08

States

09

Conditional Rendering

10

React Project Folder Structure

11

Events

12

Forms

13

Controlled and Uncontrolled Component

14

Component Life Cycles

15

Third Party Packages

16

Higher Order Components

17

React Router

18

Fetch versus Axios

19

Projects

20

Projects

21

Hooks

22

Forms Using Hook

23

Fetching Data Using Hooks

24

Project using Hooks

25

Custom Hooks

26

Context

27

Ref

28

project

29

Explore

30

Conclusions

🧡🧡🧡 HAPPY CODING 🧡🧡🧡

Support the **author** to create more educational materials  

* * *

-   Introduction
-   Requirements
-   How to Use Repo
    -   Star and Fork this Repo
    -   Clone your Fork
    -   Create a New Branch
    -   Structure Exercise Solutions
    -   Commit Exercise Solutions
    -   Update your Fork Daily
-   Setup
    -   Install Node.js
    -   Browser
        -   Installing Google Chrome
        -   Opening Google Chrome Console
        -   Writing Code on Browser Console
            -   Console.log
            -   Console.log with Multiple Arguments
            -   Comments
            -   Syntax
        -   Arithmetics
    -   Code Editor
        -   Installing Visual Studio Code
        -   How to Use Visual Studio Code

* * *

Introduction
------------

**Congratulations** on deciding to participate in 30 days of React programming challenge. In this challenge you will learn everything you need to use to develop a React application. In the end of the challenge you will get a 30DaysOfReact programming challenge completion certificate. In case you need help or if you would like to help others you may join the telegram group.

**A 30DaysOfReact** challenge is a guide for both beginners and advanced JavaScript and React developers. Welcome to 30 Days Of React. React is a JavaScript library. I enjoy using and teaching React and I hope you will do so too. In this step by step 30 Days React challenge, you will learn React which is one of most popular user interface JavaScript libraries. React can do everything that JavaScript can do. React can be used **_to add interactivity to websites, to develop mobile apps, desktop applications, games_**. I believe you will learn quite a lot in the next 30 days and your programming and problem solving skills will also be improved significantly.

I will use conversational English and less jargons to write this challenge. The content will be continuously updated. If you find a typo or grammar mistakes don't be surprised because I don't do any proof read before I publish it. I would recommend you to focus on the main message of the challenge instead of the English and some minor mistakes. I really appreciate if you send me pull requests for improvement and remember to pull first from master before you send pull requests. Most of the images I have used in this challenge came from 30DaysOfJavaScript challenge therefore you may need to rename file names and folders 30DaysOfReact. If you are good at arrays, loops, functions, objects, functional programming, destructuring and spreading and class then you will be able to follow the challenge properly. Otherwise, I strongly recommend you to check 30DaysOfJavaScript.

Before you dive into this course, you may check the review of 30 Days Of React.

This challenge is easy to read, written in conversational English, engaging, motivating and at the same time, it is very demanding. You need to allocate much time to finish this challenge. If you are a visual learner, you may get the video lesson on Washera YouTube channel. Subscribe the channel, comment and ask questions on YouTube vides and be proactive, the author will eventually notice you.

The author likes to hear your opinion about the challenge, share your thoughts about the 30DaysOfJavaScript challenge. You can leave your testimonial on this link

**Learn with Asabeneh by joining the upcoming _CODING BOOTCAMP_**

Requirements
------------

To get along with the challenge you need to have the following:

1.  Motivation
2.  A computer
3.  Internet
4.  A browser
5.  A code editor
6.  HTML, CSS and JavaScript intermediate level skill

How to Use Repo
---------------

### Star and Fork this Repo

Star this repo to support this work and Fork the repo to create your own copy to work from.

### Clone your Fork

You should always work directly from your forked copy.

# note that an \`ssh\` link is used here, but an \`https\` link will work the same
git clone git@github.com:username/30-Days-Of-React.git
cd 30-Days-Of-React

### Create a New Branch

To complete daily exercises, my suggestion is to create a separate branch to house your exercise folder or any other changes you make. This will keep your master branch clean at all times, which means your master will always be similar to the original master.

git checkout -b exercise-solutions # \`-b\` creates the branch if it does not exist

### Structure Exercise Solutions

In your new branch, you can use files/folders to structure your solutions to daily exercises

mkdir -p solutions/day-01 # \`-p\` helps create nested directories
touch solutions/day-01/level1.js # touch creates a file

### Commit Exercise Solutions

Commit your solutions to your Fork

git add solutions/day-01/level1.js
git commit -m "chore: exercise level1 complete"
git push origin exercise-solutions # branch \`exercise-solutions\` was created earlier

### Update your Fork Daily

This repo will be updated daily throughout the month. When a new day's content becomes available, you can update your forked copy with the steps below.

# 1. switch to master branch
git checkout master
# 2. check if your local copy has a link to original \`...Asabeneh/30-Days-Of-React.git\`
git remote -v
# 3. if not, add a link to original, you can choose any name for the link or use \`upstream\`
git remote add upstream git@github.com:Asabeneh/30-Days-Of-React.git
# 4. check again to confirm link added
git remote -v
# 5. now you can fetch updates from original repo, assuming you named this \`upstream\`
git fetch upstream
# 6. merge the updates to your local master branch
git merge upstream/master master
# 7. push the merged updates to your Forked copy on GitHub
git push origin master

> Note that the updates are only applied to the master branch. If you wish to update any other branch, repeat steps 6-7 with the branch name. See snippet below for `exercise-solutions` branch

git merge upstream/master exercise-solutions
git push origin exercise-solutions

Setup
-----

I believe you have the motivation and a strong desire to be a developer, a computer and Internet. In addition to that basic to intermediate level HTML, CSS and JS. If you have those, then you have everything to get started.

### Install Node.js

You may not need node.js right now but you may need it for later. Install node.js.

After downloading double click and install

We can check if node is installed on our local machine by opening our device terminal or command prompt.

asabeneh $ node -v
v12.14.0

When making this tutorial I was using node version 12.14.0, but now the recommended version of node.js for download is 12.17.0.

### Browser

There are many browsers out there. However, I strongly recommend Google Chrome.

#### Installing Google Chrome

Install google chrome if you do not have one yet. We can write small JavaScript code on the browser console, but we do not use the browser console to develop applications.

#### Opening Google Chrome Console

You can open Google Chrome console either by clicking three dots at the top right corner of the browser, selecting _More tools -> Developer tools_ or using a keyboard shortcut. I prefer using shortcuts.

To open the Chrome console using a keyboard shortcut. It is good to know the shortcut too as a JavaScript and React developer you will spend much time on a browser console and don't be lazy to open it during development.

Mac
Command+Option+J

Windows/Linux:
Ctl+Shift+J

After you open the Google Chrome console, try to explore the marked buttons. We will spend most of the time on the Console. The Console is the place where your JavaScript code goes. The Google Console V8 engine changes your JavaScript code to machine code. Let us write a JavaScript code on the Google Chrome console:

#### Writing Code on Browser Console

We can write any JavaScript code on the Google console or any browser console. However, for this challenge, we only focus on Google Chrome console. Open the console using:

Mac
Command+Option+I

Windows:
Ctl+Shift+I

##### Console.log

To write our first JavaScript code, we used a built-in function **console.log()**. We passed an argument as input data, and the function displays the output. We passed 'Hello, World' as input data or argument in the console.log() function.

console.log('Hello, World!')

##### Console.log with Multiple Arguments

The **console.log()** function can take multiple parameters separated by comma. The syntax looks like as follows:**console.log(param1, param2, param3)**

console.log('Hello', 'World', '!')
console.log('HAPPY', 'NEW', 'YEAR', 2020)
console.log('Welcome', 'to', 30, 'Days', 'Of', 'JavaScript')

As you can see from the snippet code above, _console.log()_ can take multiple arguments. It is recommended to use as many console.log() prints to check what is happening in your code but don't keep all console.log() tests on your code forever. Make your life easy by keeping the browser console open.

##### Comments

We add comments to our code. Comments are very important to make code more readable and to leave remarks in our code. JavaScript does not execute the comment part of our code.In JavaScript, any text line starting with // in JavaScript is a comment, and anything enclosed like this /\* \*/ is also a comment.

**Example: Single Line Comment**

// This is the first comment  
// This is the second comment  
// I am a single line comment

**Example: Multiline Comment**

/\* This is a multiline comment  
Multiline comments can take multiple lines  
JavaScript is the language of the web  
\*/

##### Syntax

Programming languages are similar to human languages. English or many other language uses words, phrases, sentences, compound sentences and other more to convey a meaningful message. The English meaning of syntax is _the arrangement of words and phrases to create well-formed sentences in a language_. The technical definition of syntax is _the structure of statements in a computer language._ Programing languages have syntax. JavaScript is a programming language and like other programming languages it has its own syntax. If we do not write a syntax that JavaScript understands, it will raise different types of errors. We will explore different kinds of JavaScript errors later. For now, let us see syntax errors.

I made a deliberate mistake. As a result, the console raises syntax errors. Actually, the syntax is very informative. It informs what type of mistake was made. By reading the error feedback guideline, we can correct the syntax and fix the problem. The process of identifying and removing errors from a program is called debugging. Let us fix the errors:

console.log('Hello, World!')
console.log('Hello, World!')

So far, we saw how to display text using the _console.log()_. If we are printing text or string using _console.log()_, the text has to be inside the single quotes, double quotes, or a backtick quotes. **Example:**

console.log('Hello, World!')
console.log('Hello, World!')
console.log(\`Hello, World!\`)

#### Arithmetics

Now, let us practice more writing JavaScript codes using _console.log()_ on google chrome console for number data types. In addition to the text, we can also do mathematical calculations using JavaScript. Let us do the following simple calculations. The console can directly take arguments without the **_console.log()_** function. However, it is included in this introduction because most of this challenge would be taking place in a text editor where the usage of the function would be mandatory. You can play around directly with instructions on the console.

console.log(2 + 3) // Addition
console.log(3 \- 2) // Subtraction
console.log(2 \* 3) // Multiplication
console.log(3 / 2) // Division
console.log(3 % 2) // Modulus - finding remainder
console.log(3 \*\* 2) // Exponentiation 3 \*\* 2 == 3 \* 3

### Code Editor

We can write our codes on the browser console, but it won't do for bigger projects. In a real working environment, developers use different code editors to write their codes. In this 30 days JavaScript challenge, we will be using Visual Studio Code.

#### Installing Visual Studio Code

Visual studio code is a very popular open-source text editor. I would recommend to download Visual Studio Code, but if you are in favor of other editors, feel free to follow with what you have.

If you installed Visual Studio Code, let us start using it.

#### How to Use Visual Studio Code

Open the Visual Studio Code by double-clicking its icon. When you open it, you will get this kind of interface. Try to interact with the labeled icons.

Congratulations! You have completed the setup you need to get started with React, but before we dive into React let's do a JavaScript refresher. If you are very comfortable with JavaScript you may skip day 1 JavaScript refresher. The JavaScript refresher section is vast and it may take more than one day. From my experience people usually get stuck in React because their JavaScript knowledge is very shallow therefore to fill that gap all the necessary JavaScript features which can be used in React are covered in the JavaScript refresher section. There are many exercises but you are not required to solve them. Click here if you want skip JavaScript and jump directly into React.

🎉 CONGRATULATIONS ! 🎉

Day 1 >>
