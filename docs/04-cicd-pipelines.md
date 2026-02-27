# Creating the Pipelines

We have exposed our app through an API and written unit tests. We will now create the CICD pipeline that runs automated checks on every pull request.

We will do this using GitHub Actions. In GitHub Actions, you create workflow files using YAML syntax, which are stored in the .github/workflows directory of your repository. These YAML files define the entire automation process, including when the workflow should run, what environment it needs, and the specific steps it should execute. Each workflow file can contain one or more jobs that can run sequentially or in parallel, and each job consists of individual steps that perform specific tasks.


## The PR Pipeline

When a pull request is opened against main, the workflow defined in pr-openning.yaml is triggered. It runs on a fresh ubuntu-latest runner and executes the following steps:

1. Checkout: fetch the repository code onto the runner.
2. Set up Python: install Python 3.12.
3. Install dependencies: run pip install -e . to install the package and its dependencies.
4. Run unit tests: run pytest tests/ to verify all tests pass.

This gives Pull Request reviewers information on the status of the code before it is merged.

Create a file called pr-openning.yaml inside ./github/workflows/ and add the missing steps

```bash
name: Feature Branches & PR Opening Workflow
  run-name: "Build and Test by @${{ github.actor }}"
  on:
    pull_request:
      branches:
        - main
      paths-ignore:
        - "*.md"
  permissions: read-all
  jobs:
    unit-tests:
      runs-on: ubuntu-latest
      steps:
      - uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.12'
    # TODO: Add step to install dependencies
    # TODO: Add step to run unit tests

```


Once done, create a feature branch, push it, and open a PR. If the pipeline is configured correctly you should see the checks appear on the PR as shown in figure PR running the automatic checks.<img width="619" height="294" alt="image" src="https://github.com/user-attachments/assets/7a94cfe1-f8c2-48b2-bf69-f2d4fb097208" />

Inside the Actions section of your repository you can see the individual steps running. Figure PR Pipeline Steps shows the steps.
<img width="643" height="461" alt="image" src="https://github.com/user-attachments/assets/64dce696-1428-4878-84aa-260bb8ebe4aa" />





[← Back to Main README](README.md) | [Previous: Dockerizing](03-dockerizing.md) | [Next: Conclusion →](05-conclusion.md)

