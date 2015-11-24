#Problem
* Are you tired of guessing what a JS library or framework does?
* Are you a seasoned C# developer who misses Visual Studio's intellisense?

Look no further. I will help YOU add real intellisense to your JavaScript code.

#Let's pimp-out JavaScript Intellisense

***Note***:
Taken from [John Papa's blog post](http://johnpapa.net/intellisense-witha-visual-studio-code/).

#Install 
````bash
npm install tsd -g
````

#1. Init
Create new `tsd.json` and `tsd.d.ts` files. Useful to bundle all references.

````bash
tsd init
````

#2. Install a package
Installing `knockout`

````bash
tsd install knockout --save
````
**Note**: You can run this command and not run `tsd init`. But it's good practice to run `tsd init` first.

# Results
You should have a `typings` folder with subfolder `knockout` and file `tsd.d.ts`.

Inside `tsd.d.ts`:
````javascript
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
* Clone this repo
* Find the `app.js` 
* Open it up in your favorite editor.
* Follow the instructions inside the `app.js` file
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
Visit `knockout` homepage instead:
````bash
tsd query knockout -a visit
````