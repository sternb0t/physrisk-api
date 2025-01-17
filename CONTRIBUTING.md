# Contributing to phsyrisk-api

## Getting started
To get set up, clone and enter the repo.
```
git clone git@github.com:os-climate/physrisk-api.git
cd physrisk-api
```

We recommend using [pipenv](https://pipenv.pypa.io/en/latest/) for a
consistent working environment.
```
pip install pipenv
pipenv install
pipenv shell
```

When adding a package for use in new or improved functionality,
`pipenv install <package-name>`. Or, when adding something helpful for
testing or development, `pipenv install -d <package-name>`.

## Development
Patches may be contributed via pull requests to
https://github.com/os-climate/physrisk-api.

All changes must pass the automated test suite, along with various static
checks.

[Black](https://black.readthedocs.io/) code style and
[isort](https://pycqa.github.io/isort/) import ordering are enforced
and enabling automatic formatting via [pre-commit](https://pre-commit.com/)
is recommended:
```
pre-commit install
```

To ensure compliance with static check tools, developers may wish to run black and isort against modified files.

E.g.,
```
# auto-sort imports
isort .
# auto-format code
black .
```

Code can then be tested using tox.
```
# run static checks and unit tests
tox
# run only tests
tox -e py3
# run only static checks
tox -e static
# run unit tests and produce an HTML code coverage report (/htmlcov)
tox -e cov
```

To run the application locally, run either of the following commands;
```
docker-compose up
# or
podman-compose up
```
One may then make requests of https://0.0.0.0:8080.

## Releasing
Currently, this service is released automatically to quay.io and manually
deployed onto OpenShift.
