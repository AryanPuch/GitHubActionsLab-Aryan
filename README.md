# GitHub Actions Lab

## Purpose of Each Workflow

### Workflow 1 - Job Dependencies
The purpose of this workflow is to show how jobs depend on each other in GitHub Actions.

It has three jobs: build, test, and deploy. The jobs run one after another because of the *needs* keyword.

The *test* job only runs after the *build* job finishes. And the *deploy* job only runs after the *test* job finishes.

### Workflow 2 - Multi-Platform Testing
The purpose of this workflow is to show how to run tasks on different operating systems simultaneously.

It includes three separate tasks: ubuntu-job, windows-job, and macos-job. Each task uses a different operating system
and runs on GitHub-hosted runners. Because the tasks don't depend on each other, they run in parallel.

## Key Concepts Demonstrated

### needs
The *needs* keyword creates dependencies between jobs. In Workflow 1, it ensures that jobs run in this order: build, then test, then deploy.

### env
The *env* keyword can be used to set environment variables that jobs or steps can use while running.

### runs-on
The *runs-on* keyword tells you what operating system the job will use. In this lab, I used ubuntu-latest, windows-latest, and macos-latest with the *runs-on* command.

## Challenges Faced & How I Resolved Them
One challenge was figuring out how to trigger workflows correctly. The first workflow starts when code is pushed, and the second workflow starts when a pull request is made.
At first, the second workflow didn't run because it was set to start at the wrong trigger.

Another challenge was understanding how to run jobs at the same time in the parallel way. I fixed this by removing the *needs* keyword so the jobs could run together.

After fixing these problems, both workflows worked correctly in the Actions tab.
