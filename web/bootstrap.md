# Bootstrap

[Bootstrap](http://getbootstrap.com/) is the most *popular* ( *at the time of writing* ) HTML, CSS, and JS framework for developing responsive, mobile first projects on the web.

You can get started with it by clicking [here](http://getbootstrap.com/getting-started/),
which is simply including a css and js file in your HTML page.

---
## Customizing Bootstrap
Boostrap is all open source, and can be heavily customized to meet all your demand. In the begining
I used to write additional css scripts to customize bootstrap; but the most convenient way of customizing
bootstrap is modifying is source SASS/ LESS files, and compiling them to CSS.

### Bootstrap V4 Alpha

The reason this guide is based on boostrap 4, which is in alpha right now, is because
bootstrap has finally moved to SASS instead of Less, as a CSS preprocessor.

*Starting Off :* (Taken reference from [here](http://v4-alpha.getbootstrap.com/getting-started/build-tools/#tooling-setup) )
####Build tools####

Bootstrap uses Grunt for its CSS and JavaScript build system and Jekyll for the written documentation. The Gruntfile includes convenient methods for working with the framework, including compiling code, running tests, and more.

####Tooling setup####

To use the Gruntfile and run our documentation locally, you’ll need a copy of Bootstrap’s source files, Node, and Grunt. Follow these steps and you should be ready to rock:
  
*Pre-Requisites*
  1. Download and install [Node](https://nodejs.org), which we use to manage our dependencies.
  2. Install the Grunt command line tools, *grunt-cli*, with `sudo npm install -g grunt-cli`
  3. Install [Ruby](https://www.ruby-lang.org/en/documentation/installation/), and then install a Ruby gem, "Bundler" with `sudo gem install bundler`
  
*Building the bootstrap source to compiled CSS*
  1. Clone the bootstrap source, in this case, the [V4-dev](https://github.com/twbs/bootstrap/tree/v4-dev) branch of the github repo
  2. Navigate to the root /bootstrap directory and run `npm install` to install our local dependencies listed in package.json.
  3. Run `bundle`. This will install all Ruby dependencies, such as Jekyll and Sass linter.
  4. To compile the SCSS into CSS, run `grunt` or `grunt --force` (there might be a necessity to force compile, as the
      source is in alpha stage right now)
  
---
