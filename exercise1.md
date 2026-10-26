# Exercise 11.1 - Warming up

Imagine a team of six developers building a web application in **Python** (for example with Django or FastAPI). The app is in active development and will be released soon.

## Linting, testing and building in Python

- **Linting:** Ruff is a very fast linter that can also replace flake8 and isort. Pylint is a stricter alternative. Black keeps the style consistent, and mypy checks type hints.
- **Testing:** pytest is the standard tool, usually with pytest-cov to measure coverage.
- **Building:** Python has no compile step, so "build" means packaging: a wheel created with `python -m build`, or a Docker image with the app and its dependencies. Packaging is rarely tested locally, so it is worth testing in CI.

## Alternatives to Jenkins and GitHub Actions

GitLab CI/CD, CircleCI, Travis CI, Azure DevOps Pipelines, Bitbucket Pipelines, TeamCity and Buildkite. Some are cloud services and others can be self-hosted.

## Self-hosted or cloud-based?

I would choose a **cloud-based** setup, for example GitHub Actions or GitLab CI. The team is small, the app has no special needs (like a GPU), and the configuration is only a YAML file in the repository. Nobody has to maintain servers, and for small projects the cloud is usually cheaper.

To decide for sure, I would need to know:

- How long builds and tests take, and how many builds we run per day, because cloud services charge by build time and limit resources.
- Whether there are security or legal rules about where the code and secrets can be stored.
- The budget, and whether the company already has servers and people to maintain them.

If builds are heavy or the compliance rules are strict, a self-hosted setup could be better.
