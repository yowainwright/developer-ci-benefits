![Safety Checks](https://jeffry.in/assets/developer-ci-benefits/09-safety-checks.svg?1)

# Safety Checks

Safety Checks are a catch-all for this talk. Safety Checks help communicate code and code quality. Documentation, document templates, Linting, Spell Checking, and Type Checking are all Safety Checks. These tools can be automated to run during commits, in development, or during CI.

----

> Safety Checks fall into more than 1 category of CI—feedback loop and testing.

----

## Brief Descriptions of Safety Checks

Listed below are tools that assist in checking code before submitting pull requests. Safety checks can also be incorporated into merges.

- **Committing, merging, communicating**
  - Git hook tools like [husky](https://github.com/typicode/husky) commit standardization tools like [commitizen](https://www.npmjs.com/package/commitizen), Github Templates, and Changelogs greatly help keep CI running code clean.
- **Defining Code (Type Checkers)**
  - Tools like [TypeScript](http://www.typescriptlang.org/) define and communicate code interfaces — not only types!
  - **note:** TypeScript can seem like another layer of code abstraction or learning, so be gentle on yourself and others if learning is feeling overwhelming. Though on a team like Dollar Shave Club's Front End Engineering Team, TypeScript has helped bridge experience gaps, defined shareable design team patterns, and assist developers when they're confused about what code is doing.
- **Linting**
  - Linting is the practice of allowing a tool to define code standards and patterns.
  - **ESlint (TSLint)**
    - [ESlint](https://eslint.org/) is a tool that compares a repository's JavaScript against universal standards.
    - [TSLint](https://palantir.github.io/tslint/) similar to ESlint, but for TypeScript.
  - **Stylelint**
    - [Stylelint](https://github.com/stylelint/stylelint) lints CSS.
    - [Markdownlint-cli](https://github.com/igorshubovych/markdownlint-cli), [HTMLLint](https://github.com/htmllint/htmllint) are other tools like ESlint that compare a repository's code to universal standards.
- **Writing and commenting**
  - [Write good](https://github.com/btford/write-good) helps catch grammar errors in documentation.
  - Tools like [JSDoc](http://usejsdoc.org/), [Doctrine](https://github.com/eslint/doctrine), and [TypeDoc](http://typedoc.org/) assist in writing documentation and add useful hints in code editors.
    - JSDocs and TypeDocs can compile into markdown documentation.
