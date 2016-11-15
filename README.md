# USWDS + Jekyll

This is a boilerplate for using the [U.S. Web Design Standards](https://standards.usa.gov/) to build static websites and prototypes with [Jekyll](https://jekyllrb.com/). 

Before you begin here, get acquianted with documentation for both the U.S. Web Design Standards and Jeykll. 
- [USWDS Documentation](https://standards.usa.gov/getting-started/)
- [Jekyll Documentation](https://jekyllrb.com/docs/home/)

The U.S. Web Design Standards’ entire feature set is included. You can find code snippets to copy and paste in:

```
assets/uswds/html
```

For Jekyll, there’s not much here since it’s up to you to build this out as you see fit. Only the example pages and posts have been removed. 

## Included (Coming Soon)
The following tools have been included to make front-end development easier. Read through their documentation. 
- [Bourbon](http://bourbon.io) 
- [Bourbon Neat](http://neat.bourbon.io/)

## Dependencies (Coming Soon)
You will need to install the following before you get started:
- [Jekyll](https://jekyllrb.com/docs/installation/) 
- [Sass](http://sass-lang.com/install)

## CSS
Using Sass to write your CSS is highly recommended. Your main CSS file is `assets/stylesheets/application.scss` Do not write any CSS selectors on this page. Instead, link to them with `@import` statements. 

The U.S. Web Design Standards CSS files are located in `assets/uswds/stylesheets`. You may use any Sass variables from the U.S. Web Design Standards in your project SCSS. To get familiar with the variables, you can read them in `assets/uswds/stylesheets/core/_variables.scss`

Your project CSS is located in  `assets/stylesheets/`. The `core`, `elements`, and `components` directories have been added to mirror U.S. Web Design Standards structure, but you may use whatever system you are comfortable with. 

## Javascript
jQuery and the full USWDS JS file has been included. This can probably be improved a bit since both of these libraries will add significant weight and performance hits to your page. All JavaScript are imported and concatinated into a single file, `assets/javascripts/application.js`. Importants are handled with Jekyll’s `include_relative` method. Place your scripts in `assets/javascripts/scripts` and link to them in `assets/javascripts/application.js`. 

## How to run
Using the command line, the following commands should be able to get you up and running. You will need to clone this repo, remove `origin` as a remote branch, and run on local host. 

```
$ git clone git@github.com:usds/uswds-jekyll.git
$ cd uswds-jekyll
$ git remote remove origin
$ bundle install
$ bundle exec jekyll serve
```

When the application is running, you can view the site in the browser at http://localhost:4000

