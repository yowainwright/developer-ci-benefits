# Safety Checks

Safety Checks are a catch-all for this talk. Safety Check help communicate code and code quality. Documentation, document templates, Linting, Spell Checking, and Type Checking are all Safety Checks. These tools can be automated to run during commits, in development, or during CI.

----

Safety Checks fall into more than 1 category of CI—feedback loop and testing.

----

## Brief Descriptions of Safety Checks

Described below are tools that assist in checking code before a pull requests and merges are submitted. Safety checks can also be incorporated into merges which will be described.

### Committing, merging, communicating

Tools like pre-commit, commit standard tools, Github Templates, and Changelogs greatly help in CI code committing processes.

### Defining Code (Type Checkers)

Tools like TypeScript define and communicate code interfaces—not only types!

**note:** TypeScript can seem like another layer of code abstraction or learning—so be gentle on yourself or others if learning is feeling or seeming overwhelming. Though, on a team like Dollar Shave Club's frontend, TypeScript has help bridge experience gaps, design team patterns, and assist developers when confused.

### Linting

Linting is the practice of allowing a tool to look for non-standard code issues or patterns.

#### Eslint (TS-Lint)

Eslint is a tool that compares a repository's JavaScript against universal standards.

#### Stylelint, Markdownlint

Stylelint, Markdownlint, HTMLLint are other tools, like Eslint that compare a repository's code to universal standards.

### Writing, commenting

Tools like [Write good](https://github.com/btford/write-good) can help catch spelling mistakes in documentation. Tools like JSDocs or TypeDocs can assist in writing documentation or add useful hints in Code Editors. JSDocs and TypeDocs can even compile into full documentation.
