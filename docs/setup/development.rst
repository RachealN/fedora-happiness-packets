=========================================
 Setting up a development environment
=========================================

This guide assumes that you are using a Unix-like system e.g a (GNU/)Linux distribution or macOS.

Using Docker
===============

The project comes with a Dockerfile that allows easy deployment of a web server.

#. Install Docker (refer `this <https://docs.docker.com/install/>`_) and Docker Compose (refer `this <https://docs.docker.com/compose/install/>`_) on your machine.

    For platform specific installation guidelines:

    :macOS: `Docker Desktop <https://docs.docker.com/docker-for-mac/install/>`_ (Docker Compose is included as part of desktop installs.)
    :Windows: `Docker Desktop <https://docs.docker.com/docker-for-windows/install/>`_ (Docker Compose is included as part of desktop installs.)
    :CentOS: `Docker CE <https://docs.docker.com/install/linux/docker-ce/centos/>`_
    :Debian: `Docker CE <https://docs.docker.com/install/linux/docker-ce/debian/>`_
    :Fedora: `Fedora Developer Portal <https://developer.fedoraproject.org/tools/docker/docker-installation.html>`_
    :Ubuntu: `Docker CE <https://docs.docker.com/install/linux/docker-ce/ubuntu/>`_

#. Fork the repository, then clone using ``ssh``. For steps to setup ``ssh``, refer `this <https://docs.pagure.org/pagure/usage/first_steps.html>`_ ::

    git clone "ssh://git@pagure.io/forks/<user_name>/fedora-commops/fedora-happiness-packets.git"

#. Run the client secret generation script::

    ./generate_client_secrets.sh

Although the Dockerfile runs the script to check if a client_secrets.json file is present, please generate it before starting the Docker container, so that client secrets are not being constantly generated every time the image is rebuilt.

In order to run the web server, alongside the Redis queue and celery worker instance, simply run ``docker-compose up``.
After this, you can access the local development server at ``http://localhost:8000/`` in your web browser.

If you have made any changes to the code, the Docker image must be rebuilt; this can be done my running ``docker-compose up --build``.

Since the code is being run in a container, we must enter the shell of the container in order to run tests.
Access the shell of the Docker container by running ``docker-compose exec web sh``.

The test suite can be run by running the ``t`` script, which runs the tests with the appropriate testing settings and provides a coverage report.
In order to run the script, simply type ``./t`` in the Docker container's shell.

Integration tests are run via the following command: ``docker-compose exec web ./manage.py test -v 2 -p integration_test*.py --settings=happinesspackets.settings.tsting``


Alternatives to Docker
======================

Should you be unable to run Docker, or prefer to not use it, there is an alternative way of setting up a development environment.

0. (Optional) Use a virtual environment solution, like virtualenv or Pipenv, in order to prevent dependency conflicts with other projects.
1. Install the development packages: ``pip install -r /requirements/dev.txt`` (Pipenv users can use pipenv install)
2. Export the development settings module as an environment variable: ``export  DJANGO_SETTINGS_MODULE=happinesspackets.settings.dev``
3. Generate the client_secrets.json file (This is needed in order for login functionality to work): ``./generate_client_secrets.sh``.
   If you get a permission denied error, change the file to an executable: ``chmod +x generate_client_secrets.sh``
4. Collect static resources: ``python manage.py collectstatic``
5. Ensure the database is up to date by running all migrations: ``python manage.py migrate``

In order to ensure the server is fully functional, Redis and Celery must both be configured.

Redis
------

1. Install redis from your package manager, or follow the instructions on the Redis website.
2. Ensure that the redis server has been started: ``redis-server``

Celery
_______

1. Start the celery worker in the background, or in a separate terminal window: ``celery -A happinesspackets worker -l info``


The tests can be run directly from the project folder as described in the Using Docker section, without having to run ``docker-compose exec web sh`` beforehand.

As a reference:

- Run tests with testing settings, and produce coverage report: ``./t``
- Run integration tests: ``./manage.py test -v 2 -p integration_test*.py --settings=happinesspackets.settings.tsting``

The web server can thus be run via the ``manage.py`` script: ``python manage.py runserver 0.0.0.0:8000``

When the source code is changed, the web server should automatically reload, and apply the new changes.
