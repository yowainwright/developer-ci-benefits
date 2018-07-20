# CI Configuration Init

Getting CI started for a repository takes minutes or even less! This document will focus on getting setup quickly. More detail will be provided in later documents.

----

#### Note

> Travis and Circle work very similarly. For this talk, CircleCi will be used for documentation.

----

## Automatic Setup

If test commands are already defined, CI can be implemented with no configuration. In a CI tool, like [Travis](https://travis-ci.org/) or [CircleCi](https://circleci.com/), you search for your repository a click a button that is essentially—start building with CI.

For JavaScript, CicleCi will look at `test` within a repository's `package.json` to see it valid test script is added. If it is, then CircleCi will begin running CI automatically.

## Very basic setup if Tests are not yet written

If tests aren't yet written, setting up CI can still be implemented. Below, a basic ci setup will be defined for a javascript project.

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

After those 2 steps CircleCi should pick up the `.circleci/config.yml`.

## Why is setting up even basic CI so important?

Setting up CI even with the most basic setup is extremely beneficial for time saving and code quality!

Two featured that can save developers hours per week with such small CI featuring are automatic dependency updates and build testing. These features will be discussed further in other documents.

----

#### Note

> Travis and Circle work very similarly. For this talk, CircleCi will be used for documentation.

----
