#Problem
* Are you tired of guessing what a JS library or framework does?
* Are you a seasoned C# developer who misses Visual Studio's intellisense?

Look no further. I will help YOU add real intellisense to your JavaScript code.

#Let's kick JavaScript Intellisense up a notch

Inspired by [John Papa's](http://johnpapa.net/intellisense-witha-visual-studio-code/) blog post.

#Background
>TSD is a package manager to search and install TypeScript definition files directly from the community driven DefinitelyTyped repository.

Taken directly from [TypedScript Definition website](http://definitelytyped.org/tsd/).

#Clone
Clone this repo

**Note**:
The instructions assume you already have a project. But, I have provided a sample repo to play around with.

#Steps
##1. Install TSD globally
 
````bash
npm install tsd -g
````
###1b. Install a package
If you cloned this repo, install `knockout` package. You can skip this step on your existing repo.
````bash
npm install knockout --save
````

##2. Init
Create new `tsd.json` and `tsd.d.ts` files. Useful to bundle all references.

````bash
tsd init
````

##3. Install a TypeScript Definition 
Installing TSD for `knockout`

````bash
tsd install knockout --save
````
**Note**: You can run this command and not run `tsd init`. But it's good practice to run `tsd init` first.

## Results

````pre
├── node_modules
│   └── knockout
├── typings
│   └── tsd.d.ts
├── app.js
├── package.json
├── README.md
└── tsd.json
````

Inside `tsd.d.ts`:
````typescript
/// <reference path="knockout/knockout.d.ts" />
```` 

Inside `tsd.json` (at the app root level):
````json
{
  "version": "v4",
  "repo": "borisyankov/DefinitelyTyped",
  "ref": "master",
  "path": "typings",
  "bundle": "typings/tsd.d.ts",
  "installed": {
    "knockout/knockout.d.ts": {
      "commit": "ba424f7ee39717d51c17699a09ac8df312a7e9a1"
    }
  }
}
````
#Using intellisense
Open any JavaScript file and use `knockout` with intellisense.

In this sample repo: 
* Open this repo in your favorite editor.
* Follow the instructions inside the `app.js` file.
* Have fun! 


#Other very useful commands

##Search
Simple query
````bash
tsd query knockout
````
##Open in browser
*Useful when discovering new packages (opening browser manually is for cavemen)*

Browse `knockout` definition on github 
````bash
tsd query knockout -a browse
```` 
Visit `knockout` homepage instead
````bash
tsd query knockout -a visit
````