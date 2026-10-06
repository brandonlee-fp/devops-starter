# DevOps Starter
## About
This project is a simple Python calculator created as part of a DevOps learning exercise.
## Features
The calculator supports:
- Addition
- Subtraction
- Multiplication
- Division
## How to Run
Make sure Python is installed, then run:
python calculator.py
## Author
Brandon Lee [Agnes Tachyon Cosplayer (not really)]

### Further comments on Github workflow experiments
Bandit flags assert in the test file as a low security risk. From research, it seems that in Bandit's context, raising exceptions via `if [...]: / raise [...]` seems like the superior choice.

For simplicity, a flag to exclude the unit test file was used `bandit -x ...`, an alternative suggestion from LLM-assisted tools was to use the flag to ignore low-level security risks `bandit -lll ...`.

In the 3rd to last commit, the unit test was deliberately left incorrect (assert insisted that adding `2+3=999`) to observe how workflow reacted to this. It was noted that the workflow stopped the subsequent steps as a default behaviour for workflows. Using docker/nginx-related terminology, 'directives' like `continue-on-error: true` exist to allow steps to continue progressing even on failure; but in this writer's opinion, it seems ideal that all steps in a workflow be passed for any push/pull request.
