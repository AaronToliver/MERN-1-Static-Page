# MERN-1-Static-Page
M-MongoDB, E-Express, R-React, N-Node. This repository will explain a step by step process of creating a MERN application from scratch. Following repository's will expand from this point. Check the README file for instructions.


# Intro
When building any website, whether it's a simple html/css/js project or a complex application, it's always good to have a gameplan. However, when using stacks like MERN, MEAN etc. It's even more critical to know where to start when you finally sit down and start coding. The file/folder structure for some stacks can be immensely overwhelming. Which file do we begin with? Will we be able to make changes along the way without compromising the rest of the project? How do we manage our imports/exports? The following tutorial will assist in creating a static webpage from scratch with the MERN stack as the focus.

## Before We Begin
This is NOT the first phase in a project. It isn't even the second. It is the first step in the coding phase of the project. I've had to learn that the hard way, and I'd recommend learning from my mistakes. You can save countless hours if you plan as much of your project as you can before getting to this phase. Whether it be on pen and paper, on a whiteboard with collaborators, or anything else, make sure you have at least the following in place: front-end visual concepts, back-end data concepts, and FILE STRUCTURE(<= in all caps for a reason).

# Step 1: Creating Your Project Folder
Open your command line and cd into the folder in which you would like to create your project. It can be anywhere, but it's recommended that it be somewhere you can easily access. I create a folder on my desktop for each project.
 
 ```
 $ cd /c/Users/<user_name>/Desktop/<project_folder>
 ```
 ###Note:
 This is NOT the folder in which I will begin coding the project. This contains notes, outlines, and other musings. The actuall application will be in the following folder within this one. 
 
 So I create a new folder and cd into that.
 ```
 $ mkdir <folder_name>
 $ cd <folder_name>
 ```
# Step 2: Your First File
If I've planned the project properly, I know most -if not all- of the packages I'll be using. It's okay not to have a complete idea of some of the more superficial packages like bootstrap-react or materialize, but since we know this is going to be a MERN project we can assume a few things, which leads us to our first file, package.json.

```
$ npm init
```
Go through the defaul settings. This creates the package.json file, which is the file I start for all of my projects because it documents and stores all of our dependencies.

M for MongoDB (won't be needed for this static page, but we'll install it anyways.)
```
$ npm install --save mongodb
```
E for Express
```
$ npm install --save express
```
R for React
```
$ npm install --save react react-dom
```
N for Nodejs, which we should already have as we're using it as we speak


This is where the acronym comes from. For those of you who jumped into the deep end and attempted to create a MERN application via 'npm install -g mern-cli' and then 'mern init your_new_app' you've surely seen much much more in the package.json file than this. These are devDependencies, which help us do our work along the way. I'll explain the ones we're using in our project as we install them.

...starting with Webpack
```
$ npm install --save-dev webpack
```
Since we're going to be using modular code in MERN we'll need something that translates that code into something web browsers understand. Then there's Babel...

```
$ npm install --save-dev babel-core babel-loader babel-preset-es2015 babel-preset-react
```
We'll use Babel to translate jsx extension code into something React will understand
We'll also use babel to translate some of the modern js features not yet supported natively in current browsers. Now on to Nodemon...
```
$ npm install --save-dev nodemon
```
When we change things in a Nodejs project a reset is required to reflect the changes, but with nodemon, we won't have to do that. It'll monitor our files and restart for us, saving precious time. 

Now we'll edit the node modules script feature to run webpack. It should be around line 7 in the package.json file. Change it to the following.
```
  "scripts": {
    "webpack": "webpack"
  },
```
This will allow you to run the page using webpack. It will look into the modules folder and find that command.

We're done with the package.json file for now. On to the next file.

# Step 3: index.html
Create your index.html file.
```
$ touch index.html
```
