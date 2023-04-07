# .github

Repository for boilerplate workflows and CI for python projects.

```bash
.bandit.yaml
.pre-commit-config.yaml
.github
└── workflows
```

## Contributing

Please, see [CONTRIBUTING.md](CONTRIBUTING.md) for more details on:

- using [pre-commit](CONTRIBUTING.md#pre-commit);
- following the git flow and making good [pull requests](CONTRIBUTING.md#making-a-pr).

## Using this repository

You can create new projects starting from this repository,
so you can use a consistent CI and checks for different projects.
To enable the virtual environment, use this command:

```bash
poetry install
```

To use the virtual environment, use this command:

```bash
poetry shell
```

To add a dependency, use this command:

```bash
poetry add <package>
```

When install or add dependencies, file `poetry.lock` is created. This file is used to track all dependencies used
in the project, so is a good practice commit it in the repository.

Besides all the explanations in the [CONTRIBUTING.md](CONTRIBUTING.md) file, you can use the docker-compose file
(e.g. if you prefer to use docker instead of installing the tools locally)

```bash
docker-compose run pre-commit
```
