# Running Tests and Safety Checks

Running Tests within CI is done via a `.yml` file whether [Travis](https://travis-ci.org/) or [CircleCi](https://circleci.com/) is being used. To get up and running, the checks do not require much.

----

#### Note

> Travis and Circle work very similarly. For this talk, CircleCi will be used for documentation.

----

## A brief introduction into running tests and safety checks

Most tests and safety checks are run via shell commands or cli tools. A clear introduction of CI Tools will be described in the [next document—implementing CI](). Shell commands are commands that can be run in an application like [Terminal](https://en.wikipedia.org/wiki/Terminal_(macOS)), [iTerm](https://www.iterm2.com/), or [Hyper](https://hyper.is/). Shell commands communicate directly to a computer, telling it what do to. For CI purposes, these commands mainly relate to reading files and providing information about the files to us.

### Making Sense of Running Tests and Safety Checks

A human can do all of the things CI Tests and Safety Checks do. A human can try changed code in an application to see if it works, review spelling, and look over code quality. All of that review takes a long time and is prone to human error. Apps can be used to run tests and safety checks but starting apps manually and using an app's interface takes time too but do this repeatedly also takes a lot of human time.

On the contrary to human review and manual app review, runing tests and safety commands via a shell can use apps and tools without a human involvement to achieve the same results but better. Plus, running commands can be done repeatedly within a short time frame and at an automated time frame. More information about running commands at an automated time frame will be discribed in a later document.

## Running Test and Check Examples

Listed below are visual command examples of when it looks like to run a command.

**Remove `node_modules` and re-install them**

```

rm -rf node_mdules
yarn

```

The command above will remove node modules with a shell command and then re-install them with a CLI tool command.

**Run a shell script**

```

./some-shell-command.sh

``

The `./` invokes the command and runs the script located within the file `some-shell-command.sh`.

**Run tests**

```

jest

```

[Jest](https://jestjs.io/) is a testing tool with a command line interface (CLI). A CLI astracts running commands to make it more specific to what is being done.

**Linting JavaScript**

```

eslint --fix

```

Eslint is another tool. Eslint is use review code quality of JavaScript code. Eslint also provides a CLI. The command above runs eslint. The `--fix` is an optional argument of Eslint's CLI. It fixes all issues it can without any developer changes required.

