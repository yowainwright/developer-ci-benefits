# CI Configuration Init

Getting CI started for a repository takes minutes or even less! This document will focus on getting setup quickly. More detail will be provided in later documents.

----

> Travis and Circle work very similarly. For this talk, CircleCi will be used for documentation.

----

## Starting Integration

Once code is unit tested and the developer is confident enough to submit a pull request or merge their code into a master (shared) branch, there are more safety checks to assist them in submitting code.

----

> The sentence above assumed that [git](https://git-scm.com/) is being used. Code can be submitted via alternate patterns like FTP or saving within a CMS. In those scenarios unit tests and the integrations below can still be used.

----

There are common scripts that are run in CI like safety checks, unit tests, acceptance tests and code quality checks. Review [Talk Objectives](01-talk-objectives.md) for more reference.

## Automatic Setup

CI can be setup automatically for both CircleCi and Travis! If a valid `test` command is already defined in the repository's `package.json`, CI can be implemented without any more configuration.

In a CI tool, like [Travis](https://travis-ci.org/) or [CircleCi](https://circleci.com/), the repository can be searched for after logging in or being authenticated. From there, follow the CI tool's UI to start testing.

For JavaScript, CicleCi will look at `test` within a repository's `package.json` to see it valid test script is added. If it is, then CircleCi will begin running CI automatically. Read more about setting up CircleCi automatically [here](https://circleci.com/docs/enterprise/quick-start/).

## Setting up CI Configuration

If tests aren't yet written, or if a more configured setup is needed, a configuration `.yml` file can be added for a CI tool (like CircleCi) to execute runner scripts from.

Demonstrated below is how to setup a custom CircleCi configuration with JavaScript linting (Eslint) for a CircleCi.

1. Setup linting.
   - npm install eslint --save-dev
   - within `package.json` add an eslint script, in example `"eslint:ci": "eslint ."`
1. Setup a CI configuration file
   - within a shell run `mkdir .circleci && touch .circleci/config.yml`
   - Add the following to the file:

     ```yml

      defaults: &defaults
        working_directory: ~/code
        docker:
          - image: circleci/node:10
            environment:
              NPM_CONFIG_LOGLEVEL: error # make npm commands less noisy
              JOBS: max # https://gist.github.com/ralphtheninja/f7c45bdee00784b41fed
      version: 2
      jobs:
        build:
          <<: *defaults
          steps:
            - checkout
            - run: npm i
            - run: npm run eslint:ci

     ```

After the steps above are completed and after CircleCi has been configured in Github (read about that [here](https://circleci.com/docs/2.0/), CircleCi will pick up the `.circleci/config.yml` and lint JavaScript in a CI process when a pull request is submitted.

View the [examples](examples/) folder of this repository to get ideas for configuring CI with config `.yml` files.

## Why is setting up even basic CI so important?

Setting up CI even with the most basic setup is beneficial for time savings and code quality!

Two features that can save developers hours per week with simple CI are automatic dependency updates and *build testing. Dependency updates will be discussed more [here](12-dependency-updates.md).

----

> Build testing means when `node_modules` are installed during CI by running an install, `npm install` for example, all `node_modules` install as expected. This is a simple task and **does** fail. Ensuring that `node_modules` install as expected saves considerable time for developers!

----
