# {{ cookiecutter.project_name }}

[![Build Status](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/workflows/Build%20Main/badge.svg)](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/actions)
[![Documentation](https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/workflows/Documentation/badge.svg)](https://{{ cookiecutter.github_username }}.github.io/{{ cookiecutter.project_slug }})
[![Code Coverage](https://codecov.io/gh/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/branch/main/graph/badge.svg)](https://codecov.io/gh/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }})

{{ cookiecutter.project_short_description }}

---

## Features
* ... coming soon ...

## Quick Start
```python
import {{ cookiecutter.project_slug }}
```

## Installation
**Stable Release:** `pip install {{ cookiecutter.project_slug }}`<br>
**Development Head:** `pip install git+https://github.com/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}.git`

## Documentation
For full package documentation please visit [{{ cookiecutter.github_username }}.github.io/{{ cookiecutter.project_slug }}](https://{{ cookiecutter.github_username }}.github.io/{{ cookiecutter.project_slug }}).

## Development
See [CONTRIBUTING.md](CONTRIBUTING.md) for information related to developing the code.

### Make Commands
Here are the commands you will need to know for everyday development:

```bash
  make install   # install the package in development mode
  make test      # run type checks and tests
  make view-docs # generate and view docs
  make fix-lint  # automatically format and fix lint issues
```

### Additional Steps
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
