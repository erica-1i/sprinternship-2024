# Summary

Along with a group of 3 other SWE interns, we designed and prototyped a Jobs Page feature for LinkedIn's website. We started by using Figma to design the features we thought would be helpful for users who were job-searching. We created the layout of our pages, then we moved onto coding it on an angular server using HTML and CSS.

# My contributions

I led the team of interns in using Figma by teaching my peers how to use libraries, frames, and other foundational features of Figma. 

Then, I replicated our designs using HTML and CSS. I created all the webpage layouts using flex and grid to ensure proper formatting across different screen sizes. 

# Sprinternship 2024 LinkedIn Jobs Page

Welcome to Sprinternship Linkedin Jobs Page! The simple page anyone can use to post or read others' interviews and jobs experiences! 

For the LinkedIn WiT Sprinterns 2024

# Pre-Setup

To get started with this repository, first you need to clone it, you can do that with

```shell
git clone https://github.com/shaharzeplovitch/sprinternship-2024.git
```

The GIT_REPO_LOCATION can be found with the "Code" dropdown on this page in Github

`npm` stands for Node Package Manager. Package Managers are used to install all of the related dependencies for a project. It's the same idea as `pip` in Python, Maven/Gradle in Java, or Nuget for C#.

This project uses Node.js, and node pairs with `npm` to install packages. You may not have node and npm installed on your machine by default. To check, run

```shell
node -v
```

```shell
npm -v
```

If you get something along the lines of "command not found", install Node and npm [here](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)


# Angular CLI Installation
Please install Angular CLI as it will be handy later.

```shell
npm install -g @angular/cli
```

# Installation

Once you have the repo locally, and you have Node and npm setup, we can install the dependencies for our project! This is the step you will have to do for almost any new codebase, as most code has a long list of dependencies, many of which are not obvious in the beginning! More on that in the Appendix.

This project was generated with Angular CLI which uses javascript under the hood and there is 
lot of pieces of Javascript that are needed to get this app working that you don't want to worry about. You can install them by
first opening a command line at this repo location, then running

```shell
npm install
```

Once this command finishes, you should see some new things in this repositories folder. You should now see a `package-lock.json` and `node_modules` folder in this current folder. If you don't have these two, something has gone wrong in the installation or you may be looking in the wrong folder, reach out to Shahar or your mentor to figure this out.

## Setting up JSON Server -- Get a full fake REST API with zero coding in less than 30 seconds (seriously)
JSON Server is a third party library that provides a full fake REST API (backend server API) with no database or API setup. 

You can install it by running the below command in the same terminal window
```shell
npm install -g json-server
```

In order for this to work, we will need to open up a new terminal and run our JSON Server while running our app. 

Open up a new terminal window in the same repo location as above and run

```shell
json-server --watch db.json
```

You should see the following -> 
`Loading db.json Done. Home http://localhost:3000`


Note: Make sure to keep this terminal running at all times. 

## Development server
Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

- Note:  Angular automatically detects when you have made changes to a certain file and will reload the page for you once it completes rebuilding. Sometimes, you will have to manually reload the page or restart the server if you suspect something is not right but in most cases if you don't see your changes being reflected automatically then there is either a `build error` (open up your terminal where you ran `ng serve` and see if there are any errors) or a UI bug in your code.


# Running the repo

Now that everything is installed, lets's spin it up! To do so, you can run

```shell
ng serve --open
```

You should see

`Application bundle generation complete.
Watch mode enabled. Watching for file changes...
  ➜  Local:   http://localhost:4200/`

in your command line and a window should open in your default browser with a LinkedIn logo on the top right corner. If you see this, congrats, the project is running! Time to get to work 👷‍♀️🛠


# Appendix

This section is all optional! But if you're curious feel free to read on

## Dependency chains

tl;dr: \*All code is built on top of other code. Package A requires something from package B and you can continue down the line until you get to the raw 1's and 0's that run your machine. Naturally, you as a developer do not want to worry about most of that! But there are some things you would like to know about. For Javascript projects, this is where the `package.json`, `package-lock.json` and `node_modules` come into play. Let's break these down 1 by 1

- `package.json` - This is your main entrypoint in a Javascript based project. This will tell you helpful information like what this repository is called, the author, the current version, what kind of commands this package supports under the `scripts` section, and its top level dependencies. "Top level dependencies" are the packages that this repo _directly_ requires. It _does not_ represent every package that will be needed to run this project

- `package-lock.json` - If you notice in the `dependencies` section of our `package.json`, there's weird characters next to the version number of some of our dependencies. For example: `"@angular/animations": "^17.0.0"`. These characters are important! For example, the carat `^` symbol means "at least". So when we run `npm install`, we're saying that we want _at least_ @angular/animations version 17.0.0, but if there's a newer version, we'll take that too! The idea behind this is that (leaving out some specifics about this process, called [Semantic Versioning](https://docs.npmjs.com/about-semantic-versioning)), consumers of a package would generally want the newer version of the code whenever it's available, and we don't want to have to constantly go back to our package.json to update its version numbers. So now you may be asking, well what version do we actually have installed right now? This is where the package-lock.json comes in. It records the _actual_ dependencies and their exact versions that are installed when you hit `npm install`. In the package lock, you'll also see more of the dependency chain for your project, as other top level dependencies are listed in this file

- `node_modules` - You'll notice that this folder doesn't actually exist in the repository on github, and it only appears when you do an `npm install`. That is because this folder holds the actual code of your _dependencies_. Every folder within the `node_modules` represents a dependency of your project. You can see each of the names of these dependencies is specified in your `package-lock.json`. We choose to include the `package-lock.json` instead of the `node_modules` in our Github repo because it's more efficient to just specify the versions to be installed, instead of all the code related to the dependencies themselves.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.



