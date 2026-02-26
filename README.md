# Workshop 4: Introduction to CI/CD Pipelines

This workshop teaches how to build APIs, test them, containerize with Docker, and deliver changes safely using CI/CD pipelines with GitHub Actions.

## Learning Outcomes

By the end of this lab, you will be able to:

1. Create functional APIs with FastAPI and make your code accessible over the internet.
2. Write and run unit tests with pytest and use mocks for dependencies.
3. Containerize your application with Docker for consistent deployment.
4. Create CI/CD pipelines with GitHub Actions to test, build, and deploy containers.

## Prerequisites

> [!IMPORTANT]
> This workshop for you to have completed the **Workshop 3** and have the repository on hand.

## Workflow Covered

You will work on the ML project from Workshop 3 (battery data) and add APIs, tests, and automation:

1. Expose your code through a FastAPI API.
2. Add unit tests with pytest and run them locally.
3. Dockerize the application for consistent builds.
4. Add a PR pipeline: run tests and build the image on every pull request.
5. Add a merge pipeline: publish the image and deploy to the cloud, then run end-to-end tests.

## Workshop Sections

Follow the sections in order:

1. **[Creating APIs](docs/01-creating-apis.md)**: Expose your code through APIs using FastAPI.
2. **[Unit Tests](docs/02-unit-tests.md)**: Write and run unit tests with pytest.
3. **[Dockerizing](docs/03-dockerizing.md)**: Containerize your application with Docker.
4. **[CI/CD Pipelines](docs/04-cicd-pipelines.md)**: Create PR and merge pipelines with GitHub Actions.
5. **[Conclusion](docs/05-conclusion.md)**: Deliverables and summary.
