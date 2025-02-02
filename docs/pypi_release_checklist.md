# PyPI Release Checklist

## Before Your First Release

You better visit PyPI to make sure your package name is unused.

## For Every Release

0.  Make some pull requests, merge all changes from feature branch to main.

1.  Update CHANGELOG.md manually. Make sure it follows the [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) standard.
    Be noticed that  {{ cookiecutter.repo_type | capitalize }} workflow will read changelog and extract release notes automatically.

2.  Commit the changelog changes:

    > ``` bash
    > git add CHANGELOG.md
    > git commit -m "Changelog for upcoming release 0.1.1."
    > ```

3.  Update version number and automatically create a commit, tag(can also be patch or major).

    > ``` bash
    > poetry run bump2version minor
    > ```

4.  Run the tests locally for insurance:

    > ``` bash
    > poetry run tox
    > ```

5.  Push these commits to main:

    > ``` bash
    > git push
    > ```

    Before proceeding to the next step, please check workflows triggered by this push have passed.

6.  Push the tags(created by bump2version) to main, creating the new release on both {{ cookiecutter.repo_type | capitalize }} and PyPI:

    > ``` bash
    > git push --tags
    > ```

    Only tag name started with 'v'(lower case) will leverage {{ cookiecutter.repo_type | capitalize }} release workflow.

7.  Check the PyPI listing page to make sure that the README, release
    notes, and roadmap display properly. If tox test passed, this should be ok, since
    we have already run twine check during tox test.

## About This Checklist

This checklist is adapted from <https://cookiecutter-pypackage.readthedocs.io/en/latest/pypi_release_checklist.html>.

It assumes that you are using all features of Cookiecutter PyPackage.
