![What problems does CI solve?](https://jeffry.in/assets/developer-ci-benefits/04-ci-solves-problems.svg?1)

# What problems does CI solve?

Before taking time to learn about CI, or to make a case for CI, understanding the problems CI solves is important.

---

Listed below are some of the problems that CI solves.

- When more than one developer wants to merge into a production branch at once
- When mistakes are not caught or can not be fixed before deployment
- When dependencies are out of date
- When developers have to wait extended periods of time to merge code
- When packages are dependent on other packages
- When a package is updated and must be changed in multiple places

## Illustrations of problem without CI

Illustrated below is the scope of how working without CI can quickly escalate into a large productivity problem.

----

![Legend of integration problem](https://jeffry.in/assets/developer-ci-benefits/integration-problem.svg?1)

The illustration above provides context into the symbols used for other illustrations.

----

![1 developer using multiple packages to work on one package or repository](https://jeffry.in/assets/developer-ci-benefits/1-developer-multiple-packages.svg?1)

The illustration above shows where one developer is using some dependencies to work on a repository. It might be kind of manageable at this point.
The developer has no way to know about changes with dependencies or whether their code works as expected.

----

![multiple developers using multiple packages to work on one package or repository](https://jeffry.in/assets/developer-ci-benefits/multiple-developers-multiple-packages.svg?1)

The illustration above shows where multiple developers are using some dependencies to work on a repository.
Big problems will start to arise here because dependencies could/can be updated so each developer could be working with slightly different dependencies when they try to merge.
Then, there is the problem of the code within the actual repository—how will that integrate when developers try to merge together. This will begin to take a lot of time.
The problem goes on and on. See below for more context.

![multiple developers using multiple packages to work on one package or repository which should work with multiple other packages or repositories](https://jeffry.in/assets/developer-ci-benefits/multiple-developers-multiple-packages-used-by-multiple-developers.svg?1)

----

## Illustrations of problems CI solves

Illustrated below is how CI can solve problems and as CI improves, it solves more and more problems.

----

![1 developer using CI verified code and verifying their work with CI](https://jeffry.in/assets/developer-ci-benefits/1-developer-ci-publishing.svg?1)

Above is an illustration using packages that have been verified by CI and is verifying their work as well.
This developer can generally expect the code they're relying on to work a certain way.
They're confirming the same for the code that they're publishing. They have a pretty good idea of what's going on. CI communicates that to them.

----

![1 developer using CI to publish their code](https://jeffry.in/assets/developer-ci-benefits/ci-publishing.svg?1)

The developer is feeling confident about their code because it is verified with CI. They pass publishing off to CI. The developer no longer has to manage that.
Now they may even be able to auto the setup of their updates for inheriting packages or repositories.

----

![CI is publishin and merging code](https://jeffry.in/assets/developer-ci-benefits/ci-ci-ing.svg?1)

The developer is feeling very confident about their code all around. They know when there are updates (because of tools, like [Greenkeeper](https://greenkeeper.io/)).
They know that if CI passes, their code can probably be merged right into master or a production-ready branch. They begin to use CI cron with tools like [gh-automerge](https://github.com/jonathanong/gh-automerge) to automatically merge code.
Now, the developer is mainly focused on building features, improving experiences for customers, and reading up on code updates—only when CI fails.
