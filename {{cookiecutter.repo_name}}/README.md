{{ cookiecutter.project_name }}
{{ "=" * cookiecutter.project_name|length }}

{{ cookiecutter.description }}


Requirements
------------

- nodejs


Setup
-----

First, run `npm install` to get the requisite node modules.


Usage
-----

There are a few helpful npm tasks to get things going. To run them, use `npm run
<taskname>`. To run in development mode,  `npm run watch`, then in a separate
terminal `npm run start`. The starter app should be available now at
[http://localhost:{{cookiecutter.port}}](http://localhost:{{cookiecutter.port}}). Any changes to server code the will
automatically restart the app.


To make a dist suitable for deploying to production environments, use `npm run
prod-dist`
