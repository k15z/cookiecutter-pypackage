# Cookiecutter PyPackage
This is a cookiecutter template for a Python package. Its features include:

  - Uses `mypy` for type checking.
  - Uses `pytest` and `tox` for local testing.
  - Uses `black` and `flake8` for formatting and linting.
  - Uses Github Actions for CI.
    - Testing on Ubuntu and Windows.
    - Documentation via Github Pages.
    - Automatic release to PyPI from `stable`.

It is based off [AllenCellModeling/cookiecutter-pypackage](https://github.com/AllenCellModeling/cookiecutter-pypackage) and [DAI-Lab/cookiecutter-pypackage](https://github.com/DAI-Lab/cookiecutter-pypackage) but has been heavily modified to remove unwanted functionality and add features such as type checking.

## Quickstart
To use this template use the following commands and then follow the prompts from the terminal.

```bash
pip install cookiecutter
cookiecutter gh:k15z/cookiecutter-pypackage
```

Once your project is set up, here are the commands you will need to know for everyday development:

```bash
  make install   # install the package in development mode
  make test      # run type checks and tests
  make view-docs # generate and view docs
  make fix-lint  # automatically format and fix lint issues
```

## Configuration
To take advantage of the other features - continuous integration, documentation, etc. - you will need to perform some additional steps:

  1. Add your repository to GitHub:
  2. Register your project with Codecov:
      * Make an account on [codecov.io](https://codecov.io) and click `Add new repository`
      * Copy the token provided, go to your GitHub repository's settings and under the
    `Secrets` tab, add a secret called `CODECOV_TOKEN` with the token you just copied.
  3. Generate an access token for documentation generation:
      * Go to your [GitHub account's Personal Access Tokens page](https://github.com/settings/tokens)
      * Click: `Generate new token`
      * Give the token access to: `repo:status`, `repo_deployment`, and `public_repo`.
      * Go to your GitHub repository's settings and under the `Secrets` tab, add a secret
    called `ACCESS_TOKEN` with the personal access token you just created.
  4. Register your project with PyPI:
      * Go to your GitHub repository's settings and under the `Secrets` tab, add a secret
        called `PYPI_TOKEN` with your password for your PyPI account.
      * Next time you push to the branch: `stable`, GitHub actions will build and deploy
        your Python package to PyPI.
