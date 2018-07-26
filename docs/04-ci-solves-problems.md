![What problems does CI solve?](https://jeffry.in/assets/developer-ci-benefits/04-ci-solves-problems.svg)

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

## Illustration of problem without CI

Illustrated below is the scope of how working without CI can quickly escalate into a large productivity problem.

----

![Legend of integration problem](https://jeffry.in/assets/developer-ci-benefits/integration-problem.svg)

The image above provides context into the symbols used for other illustrations.

----

![1 developer using multiple packages to work on one package or repository](https://jeffry.in/assets/developer-ci-benefits/1-developer-multiple-packages.svg)

The illustration above shows were one developer is using some dependencies to work on a repository. It might be kind of manageable at this point.
The developer has no way to know about changes with dependencies or whether their code works as expected.

----

----

![multiple developers using multiple packages to work on one package or repository](https://jeffry.in/assets/developer-ci-benefits/multiple-developers-multiple-packages.svg)

The illustration above shows were multiple developers are using a some dependencies to work on a repository.
Big problems will start to arise here because dependencies could/can be updated so each developer could be working with slightly different dependencies when they they try to merge. Then there is the problem of the code within the actual repository—how will that integrate when developers try to merge together. This will begin to take a lot of time.
The problem goes on and on. See below for more context.

![multiple developers using multiple packages to work on one package or repository which should work with multiple other packages or repositories](https://jeffry.in/assets/developer-ci-benefits/multiple-developers-multiple-packages-used-by-multiple-developers.svg)

----
