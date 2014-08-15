====================
cookiecutter-express
====================

Cookiecutter template for an ExpressJS application


Usage
-----

Generate an express app::

    cookiecutter https://github.com/wilsaj/cookiecutter-express.git

Then:

* Check the generated README in the application directory for info on how to run
  and build the app.



What's what?
------------

Server app configuration is set up using
[nconf](https://github.com/flatiron/nconf). And will be available on the
`config` object in `server/index.js` via `config.get("key")`. When the server
app initializes, it assembles its config obj so that the hierarchy for
precedence is in order of highest to lowest:

- Variables defined via config js object passed to the call to `Server()` (for
  example: `Server({port: 9000})`) come next. If you always want certain
  variables to be set and, you can throw them in here but using the
  `server/config/*.json` files described below is usually better.

- If set as ENVIRONMENT_VARIABLES 'debug' and 'NODE_ENV' will get set next.

- The values found in `server/config/secrets/<NODE_ENV>.json` are applied next
  (for example: `server/config/secrets/production.json`  will be used when
  NODE_ENV is set to "production"). This is intended to hold sensitive
  information like database user/passwords or secret API keys and such.
  It is also good for things that will change depending on the context in which
  the app is run (like testing, development and production). This secrets
  directory is put in `.gitignore` by default so you won't accidentally commit
  them.

- Finally, the values found in `server/config/defaults.json` will be set if they haven't
  already.
