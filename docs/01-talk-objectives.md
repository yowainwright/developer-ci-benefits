# Developer CI Benefits

In this talk, CI setup, road to benefits, and benefits will be discussed.

----

## Talk Objectives

This talk summarizes what continuous integration (CI) is, basic frontend setup, and how it can benefit engineers.
Hopefully this talk will provide context for developers who do not use CI — or who find CI setup challenging.
For developers experienced in integrating CI, this talk provides 1 or 2 paths to integrating CI. This talk can provide a clear path for discussion, new ideas, or even quick wins.

## A Few Items That Will Be Glossed Over

CI/CD (which stands for Continuous Integration, Continuous Delivery, and Continuous Deployment) is not very talked about. In order to provide a good base to any developer, this talk **mainly discusses CI**!
A future goal would like to follow up on this Developer CI Benefits repository with a Developer CD Benefits repository.

CI saves a lot of money. It saves money by making engineers more productive because of quicker feedback loops, auto integration, and reducing bottlenecks.

Directly correlating CI to company savings is hard because SaaS costs go up. So, if a developer wants to sell CI to the business, the formula below can be utilized.

### Time developers spend on integration and money saved

The table below provides rough context into how to calculate expected saving from implementing CI.

| Key Factor                                   | No CI Integration (no CI) | With CI Integration (with CI) | Calculation                                                                                                                                                       |
| -------------------------------------------- | ------------------------- | ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Developer points per sprint (pts)            | pts (ex: 13)              | pts (ex: 13)                  | no calculation                                                                                                                                                    |
| Developer points spent on integration  (int) | int (ex: 5)               | int (ex: 1)                   | `(<no CI int>/<no CI pts>) - (<with CI int>/<with CI pts>) = savings (number decimal)` (ex: ~30% productivity savings)                                            |
| Developers Average Salary (salary)           | salary (ex: $~100k)       | salary (ex: $~100k)           | `(<average salary> * <savings>) * <number of developers> = cost savings` (ex: ~$249,600 savings with 8 developers paid the same with a ~30% productivity savings) |

Here's a [CodePen](https://codepen.io/yowainwright/pen/wxqzMw/) that uses the calculation above.

----

> The example/formula/table above does not include developers solely focused on Integration. In a CI model, those developers after CI integration can be used throughout the rest of the development process. This can seem like a way to remove developers. However, at Dollar Shave Club in example, all developers that worked on Integration now productively work other parts of the company's code base—like faster server spin-ups—[see Dollar Shave Club's blog for more reading on this](https://engineering.dollarshaveclub.com/).

----
