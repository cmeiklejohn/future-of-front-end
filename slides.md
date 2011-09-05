!SLIDE

# The Future of Front End

Christopher Meiklejohn 
(cmeiklejohn@swipely.com)

!SLIDE

## Technologies

* coffeescript
* backbone.js
* ejs
* sass
* execjs
* rails 3.1 asset pipeline
* jasmine

!SLIDE 

## Consider this a survey talk.

!SLIDE

## Do not use them because I said so.

!SLIDE

## Awareness.
## Make informed decisions.

!SLIDE

## Dive right in!

!SLIDE

## Application

* Rails 3.1 with asset pipeline
* Developed with BDD using cucumber/rspec
* No assets

!SLIDE

## So, what are the specific goals?

* Use jasmine to BDD the front end
* Write code in *both* coffeescript and javascript
* Convert app to backbone.js application
* Have a way to run the tests effectively during development

!SLIDE 

## Brief overview of the technologies.
## Then look at the code for real world examples.

!SLIDE

## Pipeline, Sprockets, EJS

* Brief overview
* Replaces jammit
* Setup manifest files

!SLIDE

## Asset Pipeline

* Reference only as /assets
* Precompile for prod
* Recompile per hit in dev
* Reside in /public/assets, one per manifest compiled
* Compresses and stores unique asset version by SHA

!SLIDE

## Asset Pipeline

@@@ ruby

    (app|lib|vendor)/
      assets/
        javascripts
        stylesheets
        images
        templates

@@@

!SLIDE

## Figure 1: Asset Pipeline Example

!SLIDE

## Sprockets

@@@ js

    // application.js

    //= require jquery
    //= require jquery_ujs
    //= require_tree .

@@@

!SLIDE

## Figure 2: Sprockets Manifest

!SLIDE

## EJS

* Embedded javascript templates.
* app/assets/templates/index.jst.ejs
* Compiled and available as window.JST

!SLIDE

## Figure 3: EJS File

!SLIDE

## Backbone

* MVC javascript framework
* Rich front-end single page applications

!SLIDE

## No Example; Future Talk!

!SLIDE

## Coffeescript

* Language that compiles to javascript
* Syntatic sugar inspired by Haskell, Python and Ruby
* More specifically Ruby 1.9

!SLIDE

## Figure 4: Coffeescript Example

!SLIDE

## Jasmine

* Javascript BDD framework
* Developed by Pivotal Labs to replace JsUnit
* Inspired by Rspec
* Results display in browser
  * Continuous integration mode

!SLIDE

## Figure 5: Jasmine Example

!SLIDE

## How do we make this all work? (Specs)

* Write specs in javascript/coffeescript for jasmine
* Use guard to compile coffeescript specs down to javascript

!SLIDE

## How do we make this all work? (Application)

* Write my application in javascript/coffeescript 
* Use guard to recompile assets when there is a change to an asset in the pipeline
* Dev: concatenation/Prod: uglified

!SLIDE

## How do we make this all work? (Testing)

* Use the jasmine headless webkit driver to run the specs and parse the output
* Run specs against newest compiled assets in the pipeline
  * Required due to external/vendored deps, such as backbone (inefficient)

!SLIDE

## MOAR EXAMPLES!
