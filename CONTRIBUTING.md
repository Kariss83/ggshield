## I want to...

### Submit a bug report

- Make sure you can reproduce it in the latest version of GitGuardian Shield.
- Open an issue on the [issue tracker](https://github.com/GitGuardian/ggshield/issues).

### Fix an open and confirmed bug

- This bug will have a `confirmed` tag on the issue tracker.
- Leave a message on the issue tracker that you're interested in
  fixing this bug.

### Propose a new feature

- Open an issue on the [issue tracker](https://github.com/GitGuardian/ggshield/issues/new?assignees=&labels=feature+request&template=feature_request.md&title=Feature+Request) with a `feature request` label.

### Implement a new CI integration

- Open an issue on the [issue tracker](https://github.com/GitGuardian/ggshield/issues/new?assignees=&labels=CI+integration&template=feature_request.md&title=CI+Integration:).
- No core contributor review is necessary on this feature.
- Submit a Pull request

### Implement a new feature

- Follow `Propose a new feature`
- A core contributor will work out with you if it's the project's vision
  and some rudimentary specs
- Submit a Pull request

## Setup your development environment

1. Install pipenv (https://github.com/pypa/pipenv#installation)

1. Install the pre-commit framework (https://pre-commit.com/#install)

1. Fork and clone the repository

1. Install dev packages and environment

   ```sh
   $ pipenv install --dev
   ```

1. Install pre-commit hooks

   ```sh
   $ pre-commit install
   ```

1. Install pre-commit hooks for messages

   ```sh
   $ pre-commit install --hook-type commit-msg
   ```

## Testing

### Run all tests on GitGuardian Shield

Set the `TEST_GITGUARDIAN_API_KEY` environment variable to a valid GitGuardian API key.

```sh
$ make test
```

### Verify coverage of your patch

```sh
$ make coverage
$ open htmlcov/index.html
```

### Run linting locally

```sh
$ make lint
```

## Style guides

### Git commit message

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- [Use conventional commit messages](https://www.conventionalcommits.org/en/v1.0.0/#commit-message-with-scope), examples:
  - feat(integration): Add Azure Pipelines support
  - fix(ggshield): add pre-push mode header

### Python

- We're committed to support python 3.7+ for now
- Document new functions added if they're not obvious
- Black, flake and isort should keep the rest of your code standard
- If you add, update or remove dependencies, update the `Pipfile.lock` file by running `make update-pipfile-lock`
