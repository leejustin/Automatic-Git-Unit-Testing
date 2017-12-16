# Automatic Git Unit Test

## About
When set up, the scripts will automatically run your unit tests when you `commit` or `push` your code. By enforcing your tests to run, it helps ensure that you commit quality code.

Currently, there are hooks available for:
### Maven
Runs Maven tests with `mvn clean test`
### Angular
Runs Angular tests with `ng test` (I used this with Jasmine)

## Setup
For your repository, add the desired script to your git hooks directory.  This directory can be found in `REPOSITORY_ROOT/.git/hooks`.

Ensure that the proper permissions are set.  Otherwise, git will ignore the hooks.
`chmod ug+x REPOSITORY_ROOT/.git/hooks/GIT_HOOK_SCRIPT`

## Usage
The hooks will execute on `git commit` and `git push`.  Git functionality will work as normal if the test cases pass.  If they fail, then an error message will be displayed and git will not perform the desired action.

To prevent the hooks from running, run your git command with `--no-verify`.  This will perform the git action even if there are failing unit tests
Ex. `git push --no-verify`
