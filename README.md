# At Stop #

A hybrid mobile app that provides information about when the next bus will arrive at your stop. The app uses free [MTA Bus Time Developer API](http://bustime.mta.info/wiki/Developers/Index)'s to get the real-time location of the buses serving a particular stop. The app is built on top of [Ionic Framework](http://ionicframework.com/).

Comments/contributions are welcome.


### Setting up the project ###

* (Wait before cloning this repo)
* First, install [Ionic Framework](http://ionicframework.com/getting-started/).
* Second, start a new project using `ionic start atstop blank`.
* Then, in the project root (`cd atstop`):
  * Setup SASS running `ionic setup sass`.
  * Install ngCordova running `bower install ngCordova`.
  * `git init`
  * `git remote add origin PATH/TO/THIS/REPO`
  * `git fetch --all`
  * `git reset --hard origin/master`
  * `rm www/img/ionic.png www/css/style.css` files.
  * `mv www/js/config.tmpl.js  www/js/config.js`
  * run `gulp sass` to generate CSS from SCSS. Before running `gulp sass`, be sure to install all dependencies. Examples:
      * `npm install gulp-jshint --save-dev`
      * `npm install --save-dev gulp-uglify`
      * `npm install --save-dev gulp-ng-annotate`
      * `npm install gulp-uncss --save-dev`
  * run `bower install angular-inview`
  * Get a MTA Bus Time Developer API key. Go [here](http://spreadsheets.google.com/viewform?hl=en&formkey=dG9kcGIxRFpSS0NhQWM4UjA0V0VkNGc6MQ#gid=0) to request one. You will receive the key within half an hour.
  * Insert your key into the `API_KEY` field of `config.js`.
  * Set the API end point via the `API_END_POINT` constant in the same file (e.g. `http://bustime.mta.info/`)

#### Required Cordova Plugins for Building
In order to build app packages and install, several Cordova plugins are required. Using `cordova plugin add [name]`, install the following plugins:
 * cordova-plugin-network-information
 * cordova-plugin-geolocation
 * cordova-plugin-inappbrowser
 * https://github.com/whiteoctober/cordova-plugin-app-version.git

### Running
* Use the `ionic serve` function of [Ionic Framework](http://ionicframework.com/docs/guide/testing.html)
* In order to build the native mobile app, use `ionic build [platform]`

### Testing

Now, we are using [ng-describe](https://github.com/kensho/ng-describe). **Note:** `SpecRunner.html` will be deleted when all test cases are transformed to the *ngDescribe* method (For example, `www/js/filters-spec.js`).

* First, install (in the root of the project):
  * `npm install --save-dev karma`
  * `npm install -g karma-cli`
  * `npm install --save-dev karma-jasmine`
  * `npm install --save-dev karma-chrome-launcher`
  * `npm install --save-dev karma-coverage`
  * `npm install --save-dev angular-mocks`
  * `npm install --save-dev ng-describe`

If this fails on Linux with a node-gyp error, you may need to install the build-essential package

* Default Karma Config (`karma.conf.js`) file located in the root directory of the project
* Run `karma start`
* To open the coverage report page in the browser, run `open coverage/Chrome<...>/index.html`

### Project License ###
The project uses the [Apache License, version 2.0](http://opensource.org/licenses/Apache-2.0).
