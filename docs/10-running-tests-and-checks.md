# Running Tests and Safety Checks

Running Tests within CI is done via a `.yml` file whether [Travis](https://travis-ci.org/) or [CircleCi](https://circleci.com/) is being used. To get up and running, CI checks do not require much.

----

#### Note

> Travis and Circle work very similarly. For this talk, CircleCi will be used for documentation.

----

## A brief introduction into running tests and safety checks

Most tests and safety checks are run via shell commands or cli tools. Shell commands are commands that can be run in an application like [Terminal](https://en.wikipedia.org/wiki/Terminal_(macOS)), [iTerm](https://www.iterm2.com/), or [Hyper](https://hyper.is/). Shell commands communicate directly to a computer, telling it what do to. For CI purposes, these commands mainly relate to reading files and providing information about the files to us.

### Making Sense of Running Tests and Safety Checks

A human can do all of the things CI Tests and Safety Checks do. A human can try changed code in an application to see if it works, review spelling, and look over code quality. All of that review takes a long time and is prone to human error. Apps can be used to run tests and safety checks but starting apps manually and using an app's interface takes time too but do this repeatedly also takes a lot of human time.

On the contrary to human review and manual app review, running tests and safety commands via a shell can use apps and tools without a human involvement to achieve the same results but better. Plus, running commands can be done repeatedly within a short time frame and at an automated time frame. More information about running commands at an automated time frame will be described in a later document.

## Running Test and Check Examples

Listed below are visual command examples of when it looks like to run a command.

**Remove `node_modules` and re-install them**

```sh

rm -rf node_mdules
yarn

```

The command above will remove node modules with a shell command and then re-install them with a CLI tool command.

**Run a shell script**

```sh

./some-shell-command.sh

``

The `./` invokes the command and runs the script located within the file `some-shell-command.sh`.

**Run tests**

```sh

jest

```

[Jest](https://jestjs.io/) is a testing tool with a command line interface (CLI). A CLI astracts running commands to make it more specific to what is being done.

**Linting JavaScript**

```sh

eslint --fix

```

Eslint is another tool. Eslint is use review code quality of JavaScript code. Eslint also provides a CLI. The command above runs eslint. The `--fix` is an optional argument of Eslint's CLI. It fixes all issues it can without any developer changes required.

## Useful Commands to Add to Workflows

The runner scripts below are presented for quick review and use to quickly incorporate CI.ory

### Create automatic CHANGELOG.md updates

Render/Update a `CHANGELOG.md` during release

```sh

yarn add conventional-changelog-cli -D

```

Incorporating automatic `CHANGELOG.md` updates

```json

"chore:changelog": "conventional-changelog -p angular -i CHANGELOG.md -s -r 0",
"chore:pr": "git add . && git commit -m '[chore] updates changelog' --no-verify && git push origin chore-changelog -f",
"chore": "npm run chore:delete-branch && npm run chore:branch && npm run chore:changelog && npm run chore:pr",
"postpublish": "git tag $npm_package_version && git push origin --tags && npm run chore",

```

### Linting

Linting can be done for most things having to do with code. The example below provides linting opportunities for JavaScript and Markdown.

```sh

yarn add eslint markdownlint-cli -D

```

```json

"markdownlint": "markdownlint *.md",
"eslint": "eslint . --fix",
"eslint:ci": "eslint .",

```

### Fix Spelling in Markdown

Runner scripts fix spelling. The example below provides spell checking for feature rich spell checking and spell checking for CI.

```sh

yarn add markdown-spellcheck -D

```

```json

"spelling": "mdspell '**/*.md' '!**/node_modules/**/*.md' --ignore-numbers",
"spelling:ci": "mdspell '**/*.md' '!**/node_modules/**/*.md' --ignore-numbers --report",

```

### Control Gitflow

Controlling git can control the way that updates are presented within a repository.

```sh

yarn add husky -D

```

```json

"prepush": "npm test",

```

### Work on a repository grammar

Checking and fixing grammar on the fly can help ensure grammar remains (or becomes) readable.

```sh

yarn add write-good -D

```

```json

"grammar": "write-good *.md --no-passive",

```
