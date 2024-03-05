# Conditional Workflow Execution with Dependency
This GitHub Actions workflow demonstrates how to conditionally execute a workflow stage based on the outcome of a previous stage.

### Workflow Overview
The workflow consists of two stages:

- **Service Stage**: This stage performs a login or verification process and sets an output variable based on the result. If the condition is met, it sets the variable CONDITION_MATCH to true; otherwise, it sets it to false.

- **Dependent Job**: This stage depends on the outcome of the first stage. It executes only if the CONDITION_MATCH variable is set to true. Otherwise, it is skipped.

## Workflow Details

### 1) Service Stage:

- A login or verification process is performed.
- If the condition is met (for example, 1 + 1 equals 2), the output variable CONDITION_MATCH is set to true.
- Else the condition is not met (for example, 1 + 1 equals X) , the output variable CONDITION_MATCH is set to false and given stage will not run.
- If the condition is not met, the output variable CONDITION_MATCH is set to false.

### 2) Dependent Job

- This job depends on the outcome of the service stage.
- It only runs if the CONDITION_MATCH variable is set to true.
- If the condition is met, it executes the desired task. Otherwise, it is skipped.

## Workflow File

The workflow file **[job-flow.yaml](https://github.com/kuldipmori/dependant-job-github-action/blob/main/.github/workflows/job-flow.yaml)** contains the configuration for this workflow. You can modify this file according to your requirements.

## Usage

To use this workflow:

    Create a new GitHub Actions workflow file or modify an existing one.
    Copy the contents of job-flow.yaml into your workflow file.
    Commit and push the changes to your repository.

The workflow will now be triggered based on the specified events, and the stages will execute accordingly.
