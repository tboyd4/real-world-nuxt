# real-world-nuxt

> my learning nuxt app (for testing, learning, experimenting)

## Build Setup

``` bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).


# deployment instructions (to heroku) for universal mode

Heroku Server Configuration
$ heroku config:set NPM_CONFIG_PRODUCTION=false
$ heroku config:set HOST=0.0.0.0
$ heroku config:set NODE_ENV=production

Heroku Additional Setup
- add the following to the scripts in package.json
     "heroku-postbuild": "npm run build"

- add a procfile in root directory with the following code
     web: npm run start


Now you can git add, git commit, git push to heroku, and git some breakfast. 
