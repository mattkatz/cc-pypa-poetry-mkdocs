# Contributing

Contributions are welcome, and they are greatly appreciated! Every little bit
helps, and credit will always be given.

You can contribute in many ways:

## Types of Contributions

### Report Bugs

Report bugs at https://{{ cookiecutter.repo_type }}.com/{{ cookiecutter.repo_username }}/{{ cookiecutter.project_slug }}/issues.

If you are reporting a bug, please include:

* Your operating system name and version.
* Any details about your local setup that might be helpful in troubleshooting.
* Detailed steps to reproduce the bug.

### Fix Bugs

Look through the {{ cookiecutter.repo_type | capitalize }} issues for bugs. Anything tagged with "bug" and "help
wanted" is open to whoever wants to implement it.

### Implement Features

Look through the {{ cookiecutter.repo_type | capitalize }} issues for features. Anything tagged with "enhancement"
and "help wanted" is open to whoever wants to implement it.

### Write Documentation

{{ cookiecutter.project_name }} could always use more documentation, whether as part of the
official {{ cookiecutter.project_name }} docs, in docstrings, or even on the web in blog posts,
articles, and such.

### Submit Feedback

The best way to send feedback is to file an issue at https://{{ cookiecutter.repo_type }}.com/{{ cookiecutter.repo_username }}/{{ cookiecutter.project_slug }}/issues.

If you are proposing a feature:

* Explain in detail how it would work.
* Keep the scope as narrow as possible, to make it easier to implement.
* Remember that this is a volunteer-driven project, and that contributions
  are welcome :)

## Get Started!

Ready to contribute? Here's how to set up `{{ cookiecutter.project_slug }}` for local development.

1. Fork the `{{ cookiecutter.project_slug }}` repo on {{ cookiecutter.repo_type | capitalize }}.
2. Clone your fork locally

    ```
    $ git clone git@{{ cookiecutter.repo_type }}.com:your_name_here/{{ cookiecutter.project_slug }}.git
    ```

3. Ensure [poetry](https://python-poetry.org/docs/) is installed.
4. Install dependencies and start your virtualenv:

    ```
    $ poetry install -E test -E doc -E dev
    ```

5. Install the pre-commit checks that make sure your pull request merges smoothly.

    ```zsh
    pre-commit install
    ```

6. Create a branch for local development:

    ```
    $ git checkout -b name-of-your-bugfix-or-feature
    ```

    Now you can make your changes locally.

7. When you're done making changes, check that your changes pass the
   tests, including testing other Python versions, with tox:

    ```
    $ poetry run tox
    ```

7. Commit your changes and push your branch upstream to {{ cookiecutter.repo_type | capitalize }}:

    ```
    $ git add .
    $ git commit -m "Your detailed description of your changes."
    $ git push origin name-of-your-bugfix-or-feature
    ```

8. Submit a pull request through the {{ cookiecutter.repo_type | capitalize }} website.

## Pull Request Guidelines

Before you submit a pull request, check that it meets these guidelines:

1. The pull request should include tests.
2. If the pull request adds functionality, the docs should be updated. Put
   your new functionality into a function with a docstring, and add the
   feature to the list in README.md.
3. The pull request should work for Python 3.9, 3.10, and all other versions in the `pyproject.toml` file. Check
{%- if cookiecutter.repo_type == 'github' %}
   https://{{ cookiecutter.repo_type }}.com/{{ cookiecutter.repo_username }}/{{ cookiecutter.project_slug }}/actions
{%- if cookiecutter.repo_type == 'gitlab' %}
   https://gitlab.com/{{ cookiecutter.repo_username }}/{{ cookiecutter.project_slug }}/-/pipelines
{%- endif %}
   and make sure that the tests pass for all supported Python versions.

## Tips

```
$ poetry run pytest tests/test_{{ cookiecutter.pkg_name }}.py
```

To run a subset of tests.


## Deploying

A reminder for the maintainers on how to deploy.
Make sure all your changes are committed (including an entry in CHANGELOG.md).
Then run:

```
$ poetry run bump2version patch # possible: major / minor / patch
$ git push
$ git push --tags
```

{{ cookiecutter.repo_type | capitalize }} will then deploy to PyPI if tests pass.
