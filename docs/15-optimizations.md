![Optimized Builds and Developer Experience](https://jeffry.in/assets/developer-ci-benefits/15-optimizations.svg)

# Optimized Builds and Developer Experience

Optimizing builds can be approached in many ways beyond what has been discussed in this talk.

----

## Optimizing Circle Builds

The code block below provides a caching example in CircleCI to optimize CI testing time. This featuring was initially improved by [Brian Gates](https://github.com/brian-gates)

```yml

restore_build_cache: &restore_build_cache
  keys:
    - source-v1-{{ .Branch }}-{{ .Revision }}
    - source-v1-{{ .Branch }}
    - source-v1-

save_build_cache: &save_build_cache
  key: source-v1-{{ .Branch }}-{{ .Revision }}
  paths:
    - ~/code

version: 2
jobs:
  build:
    <<: *defaults
    steps:
      - restore_cache: *restore_build_cache
      - checkout
      - run: npx dsc-install-npm-token .npmrc
      - run: npm install
      - save_cache: *save_build_cache

  lint:
    <<: *defaults
    steps:
      - restore_cache: *restore_build_cache
      - checkout
      - run: npm run eslint:ci
      - run: npm run lint:templates
      - run: npx disallow

  test-server:
    <<: *defaults
    steps:
      - restore_cache: *restore_build_cache
      - checkout
      # NOTE: file-size builds the prod bundle
      # and server-node needs the prod bundle to pass tests
      - run: ./scripts/ci/file-sizes.sh
      - run: ./scripts/ci/server-node.sh
      - run: npm run test:es-check

```

### Open Source CI Optimization Tools

- **[ES-Check](https://github.com/dollarshaveclub/es-check)** by [Dollar Shave Club](https://github.com/dollarshaveclub/)
  - Compares specified bundles against ES versions. [Read more here](https://engineering.dollarshaveclub.com/futuristic-javascript-and-how-to-ensure-it-doesnt-crash-browsers-today-350df0473527#7f5e).
- **[GH-Automerge](https://github.com/jonathanong/gh-automerge)** by [Jon Ong](https://github.com/jonathanong)
  - Automatically merges passing builds using CircleCI and Github.
- **[Harmless Changes](https://github.com/dollarshaveclub/harmless-changes)** by [Dollar Shave Club](https://github.com/dollarshaveclub/)
  - helps skip unnecessary tests if the tests are not needed. The initial work for this was done by [Brian Gonzalez](https://github.com/briangonzalez).
