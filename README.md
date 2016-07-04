
# generator-elm [![Build Status](https://travis-ci.org/danneu/generator-elm.svg?branch=master)](https://travis-ci.org/danneu/generator-elm) [![NPM version](https://badge.fury.io/js/generator-elm.svg)](http://badge.fury.io/js/generator-elm) [![Dependency Status](https://david-dm.org/danneu/generator-elm.svg)](https://david-dm.org/danneu/generator-elm)

Create the minimal Elm 0.17 + Webpack project boilerplate.

## Features

- **Optional [Twitter Bootstrap (Sass) v3](http://getbootstrap.com/):**
  You can opt-in during the generator prompt.
- **Hot reloading:** File changes are pushed to the browser without a refresh.
- **[Sass](http://sass-lang.com/) support:** Just write some `.scss` files.
- **CSS vendor autoprefixing:** Automatically adds prefixes like `-webkit` to your styles when necessary.
- **Package quick-install:** The generator will prompt you for a
  space-delimited list of any extra packages you want to install at once.
  You can also invoke the generator with flags of some popular Elm packages.
  Ex: `yo elm my-app --http --websocket --svg`

## Install

    npm install -g yo generator-elm

## Generate

Generate scaffolding in a target folder:

    yo elm <destinationFolder>

Or generate in current folder:

    yo elm .

You can also supply quick-install flags for frequently-used packages:

    yo elm <destinationFolder> --http --websocket ...

Available quick-install flags:

- `--html`: elm-lang/html
- `--http`: evancz/elm-http
- `--websocket`: elm-lang/websocket
- `--svg`: elm-lang/svg
- `--markdown`: evancz/elm-markdown
- `--navigation`: elm-lang/navigation
- `--geolocation`: elm-lang/geolocation

## Run

### Development

Start the local hot-reloading development server and
visit <http://localhost:8080>.

    npm start

### Production

Bundle the app into a `dist` folder ready to be deployed.

    npm run build

    .
    └── dist
        ├── index.html
        ├── 5df766af1ced8ff1fe0a.css
        ├── 5df766af1ced8ff1fe0a.js
        └── ...

To test the production build locally, spin up a static
asset server to avoid broken links.

    $ python -m SimpleHTTPServer 5000
    server listening on http://localhost:5000

## Anatomy of the Scaffolding

Here's the generated project folder:

    .
    ├── README.md          # for your personal use, notes
    ├── elm-package.json   # elm's deps
    ├── package.json       # webpack's deps, implements the `npm` commands
    ├── src                # your elm code/components go in here
    │   └── Main.elm       # root elm component, begin hacking here
    ├── static             # holds static assets (html, css, js, img, ...)
    │   ├── css
    │   │   ├── main.scss  # root css file that should @import other css files
    │   │   └── bootstrap  # if you opted into bootstrap, can customize it here
    │   │       ├── pre-customizations.scss # tweak bootstrap $vars before it loads
    │   │       └── customizations.scss     # override bootstrap after it loads
    │   ├── img
    │   │   └── elm.png    # a dummy image
    │   ├── favicon.ico    # a default favicon for you to replace
    │   ├── index.html     # root html file, Main.elm mounts to it
    │   └── index.js       # webpack entrypoint, shouldn't need to touch
    ├── .bootstraprc       # if you opted into bootstrap, you can configure it here
    ├── webpack.config.js
    └── dist               # the stand-alone folder generated by `npm run build`
        ├── index.html     # throw the contents on a server and open index.html
        ├── <hash>.js
        └── <hash>.css

## Twitter Bootstrap (Sass) v3

Wiki: [How to work with Twitter Bootstrap](https://github.com/danneu/generator-elm/wiki/How-to-work-with-Twitter-Bootstrap)

## License

MIT © [Dan Neumann](https://github.com/danneu)
