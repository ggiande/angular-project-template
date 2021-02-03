# Steps to recreate my Angular Template using Material and Bootstrap
This project was generated with Angular CLI version 11.1.2.

I have always found it difficult to have a clean template for me to start working on Angular projects. This is my attempt at creating a template that I can clone in the future for Angular Projects.

<h2 id="quick-start">Quick Start</h2>
To run the template, clone the repo, navigate into the angular project. Run ```npm i``` to install all the dependencies. Running ```ng s``` runs the project and launches a browser on localhost on port 4200.
If you would like to recrate the template on your own, follow the directions below.

## Requirements
Before we can begin creating an Angular Project and developing our template, we need to meet the pre-requisites. If all the requirements are met, we can skip down to the [steps to recreate the template](#steps-to-recreate-the-template).
### Node.js
To install the newest version of Node.js, go to [node.js.org](https://nodejs.org/en/) and download the newest version of Node.js LTS for your machine.

npm is distributed with Node.js- which means that when you download Node.js, you automatically get npm installed on your computer. To check your version of node, run ```node --v```
### git
Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency. Git is required to install and develop Angular projects. Go to the [git scm site](https://git-scm.com/downloads) to download the latest version of git for your machine.
<h3 id="angular-header">Angular</h3>

The Angular CLI makes it easy to create an application that already works, right out of the box. Run this comamnd in a terminal window to install Angular globally ```npm install -g @angular/cli```

<h2 id="steps-to-recreate-the-template">Steps to recreate the template</h2>

If you would like to skip straight to the full html code, refer to the [template-starter](#template-starter).

Create the Angular Project
```ng new template-name```
Change directory into the Angular Project
```cd template-name```
Install the Angular Material component dev kit
```npm add @angular/cdk```
Install the dependecy for Material Design Bootstrap
```npm add angular-bootstrap-md```

<h3 id="install-bootstrap">Install Bootstrap</h3>

Place the following css link inside of the <head> tag.
```<link href="[https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css](https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css)" rel="stylesheet">``` 

Place the JSDeliver script before the end of the <body> tag.
```<script src="[https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js](https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js)"></script>``` 

- CDN via jsDelivr is the fastest way to get bootstrap going!
- Bootstrap Grid is an Optional System to flexbox
- Note that you CAN use your own [css style sheet in any component](#css)

Remove all content from src/app/app.component.html and insert the following HTML template code
```
<div class="container">
  <div class="jumbotron">
    <h1>Welcome</h1>
    <h2>Angular & Bootstrap Demo</h2>
  </div>
  <div class="panel panel-primary">
    <div class="panel-heading">Status</div>
    <div class="panel-body">
      <h3>{{title}}</h3>
    </div>
  </div>
</div>
```

Add a responsive meta-tag
```
<meta name="viewport" content="width=device-width, initial-scale=1">
```
Note: If on VSCODE, the shortcut of typing `!` inside of an HTML document will generate the following code block.

Automatically launch the project on your systems browser upon serving. Go to angular.json and add the open and port properties. `ng s` now opens a new browser upon launch.
```
        "serve": {
          "builder": "@angular-devkit/build-angular:dev-server",
          "options": {
            "browserTarget": "ng-router:build",
            "open": true,
            "port": 4200
          },
```
<h3 id="template-starter">Template Starter</h3>

If all steps were followed to a tee, this would be the new template.

```
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Separate Popper and Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.5.4/dist/umd/popper.min.js" integrity="sha384-q2kxQ16AaE6UbzuKqyBE9/u/KzioAlnx2maXQHiDX9d4/zp8Ok3f+M7DPm+Ib6IU" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.min.js" integrity="sha384-pQQkAEnwaBkjpqZ8RU1fF1AKtTcHJwFl3pblpTlHXybJjHpMYo79HY3hIi4NKxyj" crossorigin="anonymous"></script>

  </body>
</html>
```

<h2 id="css">CSS</h2>

You can add custom css to all your components by linking a css file inside your html, and referencing the source of your css inside of your component's typescript.

For instance, inside of our app-component.ts, we have a styling tag: ```styleUrls: ['./app.component.css']``` that references all css pages inside of the array.