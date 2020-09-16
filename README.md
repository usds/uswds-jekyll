# USWDS + Jekyll

A boilerplate for using the [U.S. Web Design System](https://designsystem.digital.gov/) (USWDS) v 2.8.0 and [USWDS Gulp](https://github.com/uswds/uswds-gulp) to build basic static websites and quick prototypes with [Jekyll](https://jekyllrb.com/).

For a fully-featured, officially supported gem see [18F's USWDS Jekyll project](https://github.com/18F/uswds-jekyll).

**Related docs**

- [USWDS documentation](https://designsystem.digital.gov/how-to-use-uswds/)
- [USWDS Gulp documentation](https://github.com/uswds/uswds-gulp#readme)
- [Jekyll documentation](https://jekyllrb.com/docs/home/)

## Setup

### Prerequisites

- [Ruby](https://www.ruby-lang.org/en/documentation/installation/)
  - [Bundler](https://bundler.io/)
- [Node](https://nodejs.org/)
- [Gulp CLI](https://gulpjs.com/docs/en/getting-started/quick-start)

### Install and run

```
$ npm install
$ npm start
```

After installing dependencies from NPM, `npm install` additionally runs Bundler to install Ruby gems required by Jekyll.

`npm start` runs `bundle exec jekyll start --livereload`, and spins a demo page up at `http://localhost:4000`. Changes will automatically refresh in the browser.

## Customization

### Erase demo files

The demo styles in `/assets/stylesheets/demo` and placeholder markup in `index.html` can be erased once the project is running locally.

### Stylesheets

The main SCSS manifest is `assets/stylesheets/application.scss`. USWDS theme files are imported from `assets/uswds-theme`, and USWDS is imported from `node_modules/uswds`. In this implementation, all of USWDS is imported by default. For a custom configuration, comment/uncomment the desired USWDS components in the manifest.

Project CSS is located in `assets/stylesheets/`. Create directories and `.scss` to suit project needs and `@import` them in `application.scss`. USWDS tokens/variables/etc will be accessible across custom stylesheets.

### JavaScript
JavaScript is imported and concatenated into `assets/js/application.js`. Importants are handled with Jekyll’s `include_relative` method.

Place scripts in `assets/js` and link to them in `assets/javascripts/application.js`.

## Maintenance

### Update USWDS without changing theme settings

Edit the USWDS version number in `package.json`, then ...

```
$ npm install
$ gulp update
```

`npm install` will update USWDS files (and any other dependencies, too) in `node_modules`.

`gulp update` copies fonts, images, JS, and builds SASS. It skips the `copy-uswds-setup` portion of `gulp init`, which would overwrite existing theme settings in `assets/uswds-theme`. Check that USWDS updates haven't altered the setup of theme files. Double check that updates haven't changed paths referenced in `assets/stylesheets/application.scss`.

### Reset USWDS

To reset USWDS and USWDS theme settings, run ...

```
$ gulp init
```

This will re-run the initial Gulp setup as per `gulpfile.js`. This copies USWDS files to `assets/`, including `assets/uswds-theme`. Any customization to USWDS theme settings will be overwritten with defaults.

After running, additional configuration may be needed to get `uswds-theme` working. See the [USWDS settings documentation](https://designsystem.digital.gov/documentation/settings/) for help.
