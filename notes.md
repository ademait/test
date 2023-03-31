This document is created in order to collect some tips and notions of GHA.

## Notes

* There is a `if` block. 
In the same way, we can build `else` statements by just reversing the condition. 
One way is by adding `! ${{ }}`.

* Variables are identified within the `${{ }}` block.

* Steps can re-use another action. There is an action marketplace.

* 


## Structure

Each file represents a workflow.
Files must be stored under `.github/workflows` folder.
A workflow is a configurable automated process that will run one or more jobs.
You can reference a workflow within another workflow (`uses` keyword).

A job is a set of steps in a workflow that is executed on the same runner. 
A runner is a server that runs your workflows when they're triggered. 
Each runner can run a single job at a time.
Each step is either a shell script that will be executed, or an action that will be run.
An action is a custom application for the GitHub Actions platform that performs a complex but frequently repeated task. 

Once understood some key concepts of GHA, we have to take a look at the structure of those:

* First two keywords are `name` and `run-name`.
These are optional and are used to identify the action and workflow run in the actions tab.

* `on` determine the event that triggers the workflow.

* Then we can start to define the `jobs`. 

    *  The following keyword is the name of the job.

        * Then we specify in which environment runs (`runs-on`)

        * We can also add some other keywords such as `permissions` and `if` blocks.
        
        * Right away we have the `steps` keyword, which is an array of the steps performed by the job.

            * Each step must begin with `-` (array in YAML). 

            * We can use either `uses` (along with the `with` keyword to specify the parametres) or `run` (to execute a command on the runner).

