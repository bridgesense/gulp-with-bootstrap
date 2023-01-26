# Gulp with Bootstrap Starter Kit

Gulp with Bootstrap v5 Starter Kit 

This kit was inspired by [Manjunath's work](https://github.com/lazymozek/gulp-with-tailwindcss) on a similar project.
It contains predefined gulp tasks to build out a static site
using Bootstrap 5 while making it easy to include other node modules
that might be necessary for deployment.

## Usage

1. Install Dev Depedencies

```sh
npm install // or yarn install
```

2. To start development and server for live preview

```sh
npm run dev // or yarn dev
```

3. To generate minifed files for production server

```sh
npm run prod // or yarn prod
```

## Configuration

To change the path of files and destination/build folder, edit options in **config.js** file

```sh
{
  config: {
      ...
      port: 9050 // browser preview port
  },
  paths: {
     root: "./",
     src: {
        base: "./src",
        css: "./src/css",
        js: "./src/js",
        img: "./src/img",
        font: "./src/fonts"
     },
     dev: {
         base: "./public_html",
         css: "./public_html/css",
         js: "./public_html/js",
         img: "./public_html/img",
         font: "./src/fonts"
     },
     dist: {
         base: "./public_html",
         css: "./public_html/css",
         js: "./public_html/js",
         img: "./public_html/img",
         font: "./src/fonts"
     }
  }
  ...
}
```

## Include More Files Easily 

These settings can be changed in the **gulpfile.js** file.

Live changes to this file aren't handled by `yarn dev`.

```js
const jsScripts = [
    // Add additional node modules below as in the following examples.
    // `./node_modules/jquery/dist/jquery.js`,
    // `./node_modules/jquery-validation/dist/jquery.validate.js`,
    // `./node_modules/tw-elements/dist/js/**/*.js`,

    `${options.paths.src.js}/libs/**/*.js`,
];

const externalScripts = [
    // Files in /src/js/external should be sourced separately.

    `${options.paths.src.js}/external/**/*`,
];

const tsScripts = [
    // Place custom Javascript and Typescript in the /src/js/libs directory. 

    `${options.paths.src.js}/libs/**/*.ts`,
];

const cssScssStyles = [
    // Place custom CSS and SASS files in the /src/css directory.

    `${options.paths.src.css}/**/*.scss`
];

const auxFiles = [
    // Place custom PHP and server side scripts in the /src directory where needed.

    `${options.paths.src.base}/**/{*.,.}{htaccess,php,txt}`
];
...
```
