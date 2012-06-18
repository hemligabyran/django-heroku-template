# {{ project_name|title }} Django Project #

## Prerequisites ##

- python >= 2.5
- pip
- virtualenv/wrapper (optional)
- foreman (gem)
- heroku (gem)

## Installation ##

### Creating the environment ###

Create a virtual python environment for the project.
If you're not using virtualenv or virtualenvwrapper you may skip this step.

#### For virtualenvwrapper ####

```mkvirtualenv --no-site-packages {{ project_name }}-env```

#### For virtualenv ####

```virtualenv --no-site-packages {{ project_name }}-env```

```cd {{ project_name }}-env```

```source bin/activate```

### Install requirements ###

```cd {{ project_name }}```

```pip install -r requirements.txt```

### Create app at heroku ###

```heroku apps:create -s cedar {{ project_name}}```

Add sendgrid addon to your heroku app, to enable sending of emails (optional)

```heroku addons:add sendgrid:starter```

Add sentry addon to your heroku app, to enable exception logging (optional)

```heroku addons:add sentry:developer```

### Configure project ###

Edit file ```.env```

### Sync database ###

```foreman run python {{ project_name }}/manage.py syncdb```

## Running ##

```foreman start```

Open browser to 127.0.0.1:5000
