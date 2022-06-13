# Installation

## Stable release

To install {{ cookiecutter.project_name }}, run this command in your
terminal:

``` console
$ pip install {{ cookiecutter.project_slug }}
```

This is the preferred method to install {{ cookiecutter.project_name
}}, as it will always install the most recent stable release.

If you don't have [pip][] installed, this [Python installation guide][]
can guide you through the process.

## From source

The source for {{ cookiecutter.project_name }} can be downloaded from
the [{{cookiecutter.repo_type | capitalize }} repo][].

You can either clone the public repository:

``` console
$ git clone git://{{cookiecutter.repo_type}}.com/{{ cookiecutter.repo_username }}/{{ cookiecutter.project_slug }}
```

Or download the [archive][]:
{%- if cookiecutter.repo_type == 'github' %}
``` console
$ curl -OJL https://github.com/{{ cookiecutter.repo_username }}/{{ cookiecutter.project_slug }}/tarball/main
```
{%- if cookiecutter.repo_type == 'gitlab' %}
``` console
$ curl -OJL https://gitlab.com/{{ cookiecutter.repo_username }}/{{ cookiecutter.project_slug }}/-/archive/main/{{ cookiecutter.project_slug }}-main.tar
```
{%- endif %}


Once you have a copy of the source, you can install it with:

``` console
$ pip install .
```

  [pip]: https://pip.pypa.io
  [Python installation guide]: http://docs.python-guide.org/en/latest/starting/installation/
  [{{cookiecutter.repo_type | capitalize }} repo]: https://%7B%7B%20cookiecutter.repo_type%20%7D%7D.com/%7B%7B%20cookiecutter.repo_username%20%7D%7D/%7B%7B%20cookiecutter.project_slug%20%7D%7D
{%- if cookiecutter.repo_type == 'github' %}
  [archive]: https://github.com/%7B%7B%20cookiecutter.repo_username%20%7D%7D/%7B%7B%20cookiecutter.project_slug%20%7D%7D/tarball/main
{%- if cookiecutter.repo_type == 'gitlab' %}
  [archive]: https://gitlab.com/%7B%7B%20cookiecutter.repo_username%20%7D%7D/%7B%7B%20cookiecutter.project_slug%20%7D%7D/-/archive/main/%7B%7B%20cookiecutter.project_slug%20%7D%7D-main.tar
{%- endif %}
