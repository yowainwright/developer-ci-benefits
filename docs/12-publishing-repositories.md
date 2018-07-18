# Publishing Repositories

Publishing packages, even if the only dependents are an orgs dependents can be very valuable. With a few steps packages can be published publically or privately.

----

> There are a few more options besides publishing npm packages if that is not possible. This will be discussed below.

----

## NPM Publishing

Being able to publsh npm packages assumes a basic understanding package managers, npm's cli, and npm's `package.json`.

### Level setting

The list below provides basics of setting up a NPM package.

- `npm init` instatiates a series of prompts which will help to make a repository's `package.json`
- within a `package.json` file there are core objects and keys that are discussed regularly: configuration, dependencies, meta, and scripts
  - **configuration:** things like jest setup
  - **dependencies:** npm packages that repository is dependent on
  - **meta:** a packages description, name, and tags
  - **scripts:** commands to run on a repository like starting a server and testing
- `npm test` package tests
- `npm start` is mainly used to start a server

### Publishing

NPM publishing can be done with one command `npm publish`. There are a few things that are good to be aware of when publishing.

- **Name:** the npm package name is important because it must be unique
- **Scope:** npm packages can be private or public. This is generally referenced by the word _scope_. Scope does not directly relate to where a NPM package is private or public but only a scoped package can be private.
- **Audience:** before publishing, knowing the audience is extremely important for multiple reasons, but security comes to mind first.

## Private NPM Publishing

Private npm publishing can also be done with one command—`npm publish`. The only thing that initially makes a package private is whether it is scoped or not.

Private npm packages require that the publisher be a member of organization. A 404 message will be received if a non-member of a scoped package tried to publish.

Private npm packages can be made publish within the [npmjs.com](https://npmjs.com) ui
or by running `npm access restricted <package_name>`.

You can read more detail about [private npm in the npm docs](https://docs.npmjs.com/private-modules/intro).

## NPM Publishing with CI

NPM can be published in CI by adding configuration steps within the CI to do so.

