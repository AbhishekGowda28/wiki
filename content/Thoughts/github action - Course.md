---
categories:
  - "[[Programming]]"
  - "[[Pluralsight]]"
  - "[[Notes]]"
publish: true
---

> [!goal] Deep understanding of github actions

# github action - Course

## Background-Current knowledge

I've used github actions only once for one of my project. It would run the unit test and display the status of the unit test.
In one of my latest project, which I archieved later - coding adventrues I tried to host github pages from github action but failed to do so.

## Taxanomy

### What is github actions?

It is a workflow that needs to executed on certain actions. The executions are called **jobs**, a single action can be called a workflow.
**Runner**
A virtual machine, where the jobs defined in the workflows are run. The runners have a fixed time to be online, and once they complete the scheduled time, machines are offline.
They span up on every actions or defined actions where they need to be spun up.

### Sample code

```yaml
name:  Sample 

on: push

jobs: 
	build:
		runs-on: ubuntu-latest
		steps:
			name: sample echo
			run: echo "sample echo"
```

This is to run on the runner without using any actions defined by others.
If we want to use the actions defined by others we will replace `run: <command>` with `uses: <action_name>`

Example

```yaml
steps:
	name: checkout code runner
	uses: actions/checkout@v2
```

---

> [!important]- Don't give permissions unnecessarily for actions/runners.
> Be mindful before giving permissions

A small independent jobs can be helpful, when they fail re-running them would be easier to fix the pipeline

**Branching strategy**

- Protect key branches

**Microservice**

---

- Learnt how to create releases from git-pipelines

- Learnt how to checkout code

- Learnt how to create & publish artifacts

- learnt about github variables

- Actions can be only of YAML format

- Job descriptions can be defined in any order. To have one job to be executed

- There are community created actions that can be helpful.

- Actions doesn't provide support for python packages
