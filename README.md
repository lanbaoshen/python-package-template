# Python Package Template

A really simple to start project template for Python Package Projects.

## What is included on this template

- `uv` as the main dependency manager and build tool.
- `pytest` for testing.
- `ruff` for linting and code formatting.
- `pre-commit hook` to control the quality of the code before commiting.
- `zensical` for documentation.
- `mkdocstrings` for generating documentation from code.
- `github actions` for run tests, publish package to PyPI and generate documentation on GitHub Pages.

## How to use this template

1. Click the "Use this template" button on GitHub to create a new repository based on this template.
2. Give your new repository a name and description, then click "Create repository".
3. Then clone your new project to your local machine and navigate to the project directory.
4. You should modify the `pyproject.toml` file to set your package name, version, description, author, etc.
5. Now enjoy coding your new Python package!

## Install the dependencies

To install the dependencies, you can use `uv`:

```shell
uv sync --all-groups
```

## Git commit template

```shell
git config commit.template .gitmessage.txt
```

## pre-commit hook

```shell
pre-commit install

pre-commit run --all-files
```

## Pytest

```shell
uv run pytest --cov=src
```

## Docs

To preview the documentation locally, you can use `zensical`:

```shell
zensical serve
```

You need to set the repo GitHub page from branch to `Github Actions`:

1. Go to your repository on GitHub.
2. Click on `Settings` in the top menu.
3. In the left sidebar, click on `Pages`.
4. Under `Build and deployment`, select `Source` as `GitHub Actions`.

After you push a new tag to your repository, the GitHub Action will automatically generate the documentation and publish it to GitHub Pages.

## PyPI
You need to create an account on [PyPI](https://pypi.org/) and get your API token.
Then you need to add your API token to the `UV_PUBLISH_TOKEN` secret on your GitHub repository:

1. Go to your repository on GitHub.
2. Click on `Settings` in the top menu.
3. In the left sidebar, click on `Environments`.
4. Click on `New Environment` and set the environment name to `pypi`.
5. Click on `Add environment secret` and set the name to `UV_PUBLISH_TOKEN` and the value to your API token.
6. Click on `Add secret` to save the secret.

Now, when you push a new tag to your repository, the GitHub Action will automatically publish your package to PyPI using the API token you provided.
