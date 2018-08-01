![Documentation and Feedback Tooling](https://jeffry.in/assets/developer-ci-benefits/06-doc-tooling.svg?1)

# Documentation and Feedback Tooling

Documentation is a key part of implementing CI. There are many patterns for documentation. The great news is that Github provides standard templates and there is a lot of content that can be copied to get documentation setup quickly.

---

> Documentation is in the [Feeback Loop](02-what-is-ci.md) category of CI.

---

## Standard Documents

Listed below are standard documents to describe a repository. These documents are related to CI because they can offer a quick introduction to a project.

- **README:** the _README_ is general a markdown file that provides information about a repository
- **CHANGELOG:** the _CHANGELOG_ is a markdown file describes changes within a repository
- **CODE_OF_CONDUCT:** the _CODE OF CONDUCT_ is a markdown file that dictates expected communication patterns within repository pull requests and issues
- **LICENSE:** the _LICENSE_ is a text file that dictate rules of law to protect a repository

### `.github` TEMPLATES

Github Templates that are placed within a `.github` folder.
Each template is automatically presented based on Github interactions.

- **CONTRIBUTING:** the _CONTRIBUTING TEMPLATE_ is an auto-reply markdown template that provide repository contributing context by referencing CODE OF CONTENT and maybe guidelines to successful contribution
- **ISSUE_TEMPLATE:** the _ISSUE TEMPLATE_ is an auto-reply markdown template that appears after a developer submits an issue
- **PULL_REQUEST_TEMPLATE:** the _PULL REQUEST TEMPLATE_ is an auto-reply markdown template that appears when a developer submits a pull request

### Standard Documents reference materials

Listed below are materials for learning more about Standard Documents that should be in code repositories.

- **Github Blog Posts and Help Pages**
  - Github provides blog posts and help pages for using `.github/TEMPLATES`
    - [Github Blog Post on `.github/TEMPLATES`](https://blog.github.com/2016-02-17-issue-and-pull-request-templates/)
    - [ISSUE templates](https://help.github.com/articles/manually-creating-a-single-issue-template-for-your-repository/)
    - [About ISSUE templates](https://help.github.com/articles/about-issue-and-pull-request-templates/)
    - [CONTRIBUTING templates](https://help.github.com/articles/setting-guidelines-for-repository-contributors/)
    - [PULL REQUEST template](https://help.github.com/articles/creating-a-pull-request-template-for-your-repository/)
- **Awesome Lists**
  - Awesome lists are Github repositories dedicated to listing resources on particular subjects
    - [Awesome Github Templates](https://github.com/devspace/awesome-github-templates)
    - [Awesome READMEs](https://github.com/matiassingers/awesome-readme)
- **[Contributor Covenant](https://www.contributor-covenant.org/)**
  - The goto source for providing a [CODE OF CONDUCT](https://www.contributor-covenant.org/version/1/4/code-of-conduct.md) for a repository.
- **[HEARTLY](https://github.com/heartly)**
  - Heartly provides tools to make coding a bit more friendly

## Quickly Setting Up Documentation Basics

Listed below are quick steps that can be copied and pasted with your own minor updates to get documentation setup quickly.

- Copy this [`README.md` template](https://raw.githubusercontent.com/heartly/heartly-readme-boilerplate/master/files/DEFAULT_README.md) from Heartly and update as needed
- Create a blank `CHANGELOG.md` `touch CHANGELOG.md`.
  - A script to automatically create the CHANGELOG.md will be added
  - The [Running Tests and Checks doc](10-running-tests-and-checks.md) will cover how the CHANGELOG.md can be automatically updated
- Copy the [`CODE_OF_CONDUCT.md`](https://www.contributor-covenant.org/version/1/4/code-of-conduct.md) from [Code Covenant](https://www.contributor-covenant.org/version/1/4/code-of-conduct)
- A LICENSE `.txt` file should be added when a repository initializes. If it is not, it can be copied [here](https://opensource.org/licenses/MIT)
- Within a created `.github/` folder:
  - Add an `ISSUE_TEMPLATE.md`
    - This [`ISSUE_TEMPLATE.md`](https://raw.githubusercontent.com/stevemao/github-issue-templates/master/simple/ISSUE_TEMPLATE.md) from [Steve Mao](https://github.com/stevemao) can be copied for quick setup.
  - Add a `PULL_REQUEST_TEMPLATE.md`
    - This [PULL_REQUEST_TEMPLATE.md](https://raw.githubusercontent.com/stevemao/github-issue-templates/master/simple/PULL_REQUEST_TEMPLATE.md) from [Steve Mao](https://github.com/stevemao) can be copied for quick setup.
  - `ISSUE_TEMPLATE.md` and `PULL_REQUEST_TEMPLATE.md` will be automatically populated when their correlated action is initialized (for example, when a pull request is submitted).

## An Aside on Documentation

Documentation? I say "YES" always! There is debate around "how to document" and "documentation best practices". Books like [Clean Code](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) provide a lot of thoughts on documents and code comments. I find documentation to be valuable because it can provide context beyond code. Think business objectives that affect code quality. Even a comment that is not updated after the code has been updated provides context when integrated within git. There are great points that disagree with the sentiment of the sentences above on documentation. The general sentiment for this talk is _anything_ that prevents/helps with non-manual work giving developers more opportunity to work.
