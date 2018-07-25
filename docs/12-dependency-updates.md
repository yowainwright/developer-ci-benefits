# Dependency updates

One of the huge benefits of basic CI is automatic dependency updates with tools like [Greenkeeper](https://greenkeeper.io/).

## What are automatic dependency updates?

Often code in repositories is dependent on code within packages. Referencing and using code from other packages speeds up the development process. In JavaScript, code from other packages is referenced within a  `package.json` file. Dependency update tools like Greenkeeper monitory a repository's dependency packages for updates. If a dependency package is updated and Greenkeeper is enabled, it will submit a pull request within the repository which will trigger CI.

This is greatly beneficial for developers because dependencies can be kept up to date much more easily.

----

> Packages are modules of code that can be imported into dependent repositories. In example, when building a ship with legos, different blocks of legos are used to build the ship. It doesn't matter whether a unique block was initially meant for another ship, came by itself, or was for the ship, If the block is the right shape, contains the correct amount of pegs, and is the correct color—it can be used to make the ship!

----

## Breaking down dependencies

Packages have a corresponding semver numbers that is generally defined by 3 numbers and dots. Here's an example for reading clarity, `1.2.3`. These numbers can be followed by a `-` with other information. For the purposes of this talk, only the first 3 numbers will be discussed.

Here's the number references again so that it can be reviewed in greater detail:

```txt

1.2.3

```

- The `1` represents a major version. This will only be changed with major updates. If this number is change, updates should be reviewed carefully.
- The `2` represents a feature version. This represents a new update that should not affect the way that code is working currently
- The `3` represents a minor update or patch. This update is made when dependencies are updated, bugs are fixed, or something is optimized but isn't new or doesn't affect the package with how it is used.

## What are the weird things in front of the numbers?

There are a few things that are placed in front of version numbers that allow npm to download new packages approximately.

- **`^`**: The up caret down the latest feature version of packages
  - if the package looks like this `^1.1.0` and the latest version is `1.5.0`, npm will download `1.5.0`.
- **`~`**: The tilde downloads the the latest patch version of packages
  - if the package looks like this `~1.0.1` and the latest version is this `1.0.5`, npm will download `1.0,5`
