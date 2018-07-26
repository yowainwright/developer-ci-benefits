![Publishing Repositories](https://jeffry.in/assets/developer-ci-benefits/13-publshing-repositories.svg)

# Publishing Repositories

Publishing packages, even if the only dependencies are an organization's dependencies, can be very valuable. With a few steps, packages can be published publicly or privately.

---

> There are a few more options besides publishing npm packages if that is not possible. This will be discussed below.

---

## NPM Publishing

Being able to publish NPM packages assumes a basic understanding of package managers, NPM's cli, and NPM's `package.json`.

### Level setting

The list below provides basics of setting up an NPM package.

- `npm init` instantiates a series of prompts which will help to make a repository's `package.json`
- within a `package.json` file, there are core objects and keys that are discussed regularly: configuration, dependencies, meta, and scripts
  - **configuration:** things like jest setup
  - **dependencies:** NPM packages that a repository is dependent on
  - **meta:** a package's description, name, and tags
  - **scripts:** commands to run on a repository like starting a server and testing
- `npm test` package tests
- `npm start` is mainly used to start a server

### Publishing

NPM publishing can be done with one command `npm publish`. There are a few things that are good to be aware of when publishing.

- **Name:** the NPM package name is important because it must be unique
- **Scope:** NPM packages can be private or public. This is generally referenced by the word `_scope_`. Scope does not directly relate to where an NPM package is private or public but only a scoped package can be private.
- **Audience:** before publishing, knowing the audience is extremely important for multiple reasons, but security comes to mind first.

## Private NPM Publishing

Private NPM publishing can also be done with one command: `npm publish`. The only thing that initially makes a package private is whether it is scoped or not.

Private NPM packages require that the publisher be a member of an organization. A 404 message will be received if a non-member of a scoped package tries to publish.

Private NPM packages can be published within the [npmjs.com](https://npmjs.com) ui or by running `npm access restricted <package_name>`.

You can read more detail about [private NPM in the NPM docs](https://docs.npmjs.com/private-modules/intro).

## NPM Publishing with CI

NPM can be published in CI by adding configuration steps within the CI to do so.

These build steps look something like this:

```yml
publish:
    <<: *defaults
    steps:
      - checkout
      - run: npm install
      - run:
          name: NPM Access ($NPM_WRITE_TOKEN set in Circle)
          command: echo "//registry.npmjs.org/:_authToken=$NPM_WRITE_TOKEN" >> ~/.npmrc
      - run: git config --global user.email "circle@dontemailme.com" && git config user.name "CircleCI"
      - run: npm run update-tag
      - run: npm publish
```

Then, NPM write tokens can be added to a `.npmrc`.
This example can be viewed [here](examples/ember-engine-circle-config.yml).
