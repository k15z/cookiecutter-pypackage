.PHONY: clean clean-test clean-pyc clean-build docs help
.DEFAULT_GOAL := help

define BROWSER_PYSCRIPT
import os, webbrowser, sys

try:
	from urllib import pathname2url
except:
	from urllib.request import pathname2url

webbrowser.open("file://" + pathname2url(os.path.abspath(sys.argv[1])))
endef
export BROWSER_PYSCRIPT

define PRINT_HELP_PYSCRIPT
import re, sys

for line in sys.stdin:
	match = re.match(r'^([a-zA-Z_-]+):.*?## (.*)$$', line)
	if match:
		target, help = match.groups()
		print("%-20s %s" % (target, help))
endef
export PRINT_HELP_PYSCRIPT

BROWSER := python -c "$$BROWSER_PYSCRIPT"

help:
	@python -c "$$PRINT_HELP_PYSCRIPT" < $(MAKEFILE_LIST)

clean:  ## clean all build, python, and testing files
	rm -fr build/
	rm -fr dist/
	rm -fr .eggs/
	find . -name '*.egg-info' -exec rm -fr {} +
	find . -name '*.egg' -exec rm -f {} +
	find . -name '*.pyc' -exec rm -f {} +
	find . -name '*.pyo' -exec rm -f {} +
	find . -name '*~' -exec rm -f {} +
	find . -name '__pycache__' -exec rm -fr {} +
	rm -fr .tox/
	rm -fr .coverage
	rm -fr coverage.xml
	rm -fr htmlcov/
	rm -fr .pytest_cache

install:  ## install in development mode
	pip install -e .[dev]

fix-lint:  ## automatically fix lint and format
	isort -rc {{cookiecutter.project_slug}} tests
	black {{cookiecutter.project_slug}} tests

test:  ## run type check and tests
	flake8 {{cookiecutter.project_slug}}
	mypy {{cookiecutter.project_slug}}
	pytest

test-all:  ## run tests using tox
	tox

docs:  ## generate docs
	rm -f docs/{{cookiecutter.project_slug}}*.rst
	rm -f docs/modules.rst
	sphinx-apidoc -M -o docs/ {{cookiecutter.project_slug}}
	$(MAKE) -C docs html

view-docs:  ## generate docs and open in browser
	make docs
	$(BROWSER) docs/_build/html/index.html
