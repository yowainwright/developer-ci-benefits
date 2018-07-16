# Dependency updates

One of the huge benefits of basic CI is automatic dependency updates with tools like [Greenkeeper](https://greenkeeper.io/).

## What are automatic dependency updates?

Often code in repositories is dependent on code from packages. Referencing and using code from other packages speeds up the development process. In JavaScript, code from packages referenced within a  `package.json` file. Dependency update tools, like Greenkeeper monitory a repository's dependency packages for updates. If a dependency package is updated, Greenkeper will submit a pull request within a repository which will trigger CI. If CI passes, the updated dependency will be referenced in future builds.

This is greatly beneficial for developers because dependencies can be kept up to date much more easily.

## Breaking down dependencies

Packages have a corresponding semver number that is genearally defined by 3 numbers and dots. Here's an example for reading clarity, `1.2.3`. These numbers can be followed by a `-` with other information. For the purposes of this talk, only the first 3 numbers will be discussed.

Here's the number references again so that it can be reviewed in greater detail:

```sh
1.2.3
```

- The `1` represents a major version. This will only be changed with major updates. If this number is change, updates should be reviewed carefully.
- The `2` represents a feature version. This represents a new update that should not affect the way that code is working currently
- The `3` represents a minor update or patch. This update is made when dependencies are updated, bugs are fixed, or something is optimized but isn't new or doesn't affect the package with how it is used.

## What are the weird things in front of the numbers?
