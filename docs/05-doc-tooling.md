# Documentation and Feedback Tooling

Documentation is a key part of implementing CI. There are many patterns for documentation. The great news is that Github provides standard templates and there is a lot of content that can be copied to get documentation setup quickly.

## Standard Documents

Listed below are standard documents use to describe a repository. These documents are related to CI because the can offer a quick introduction to a project making it easy for other developers to get up to speed within a repository.

### STANDARD DOCUMENTATION

Standard files used to document a repository. These files site at the top level of a repository.

- **README:** the README is general a markdown file that provides information about a repository
- **CHANGELOG:** the CHANGELOG is a markdown file describes changes within a repository
- **CODE_OF_CONDUCT:** the CODE OF CONDUCT is a markdown file that dictates expected communication patterns within repository pull requests and issues
- **LICENSE:** the LICENSE is a text file that dictate rules of law to protect a repository

### `.github` TEMPLATES

Templates that are placed within a `.github` folder. Each template is automatically presented based Github interactions.

- **CONTRIBUTING:** the CONTRIBUTING template is an auto-reply markdown template that provide repository contributing context by referencing CODE OF CONTENT and maybe guidelines to successful contribution
- **ISSUE_TEMPLATE:* the ISSUE template is an auto-reply markdown template that appears after a developer submits an issue
- **PULL_REQUEST_TEMPLATE:** the PULL REQUEST TEMPLATE is an auto-reply markdown template that appears when a developer submits a pull request

### Reference Materials

Listed below are materials for learning more about repository documentation.

- **Github Blog Posts and Help Pages**
  - Github provides blog posts and help pages for using `.github/TEMPLATES`
    - [Github Blog Post on `.github/TEMPLATES`](https://blog.github.com/2016-02-17-issue-and-pull-request-templates/)
    - [ISSUE templates](https://help.github.com/articles/manually-creating-a-single-issue-template-for-your-repository/)
    - [About ISSUE templates](https://help.github.com/articles/about-issue-and-pull-request-templates/)
    - [CONTRIBUTING templates](https://help.github.com/articles/setting-guidelines-for-repository-contributors/)
    - [PULL REQUEST template](https://help.github.com/articles/creating-a-pull-request-template-for-your-repository/)
- **Awesome Lists**
  - Awesome lists are Github repositories dedicated to listing resource on particular subjects
    - [Awesome Github Templates](https://github.com/devspace/awesome-github-templates)
    - [Awesome READMEs](https://github.com/matiassingers/awesome-readme)
- **[Contributor Covenant](https://www.contributor-covenant.org/)**
  - The goto source for providing a [CODE OF CONDUCT](https://www.contributor-covenant.org/version/1/4/code-of-conduct.md) for a repository.
- **[HEARTLY](https://github.com/heartly)
  - Heartly provides tools to make coding a bit more friendly

## Quickly Setting Up Documentation Basics

Listed here are quick steps that can be copy and pasted with minor updating to get documentation of to a good start for CI support.

- [Copy this **README.md template**](https://raw.githubusercontent.com/heartly/heartly-readme-boilerplate/master/files/DEFAULT_README.md) from Heartly and update as needed
- Create a blank **CHANGELOG.md** `touch CHANGELOG.md`.
  - A script to automatically up the CHANGELOG.md will be added in the [Running Tests and Checks doc](https://github.com/yowainwright/developer-ci-benefits/blob/master/docs/09-running-tests-and-checks.md).
- [Copy the **CODE_OF_CONDUCT.md**](https://www.contributor-covenant.org/version/1/4/code-of-conduct.md) from [Code Covenant](https://www.contributor-covenant.org/version/1/4/code-of-conduct).
- A LICENSE Text file should be added when the repository was initialize. If it was not, it can be copied [here](https://opensource.org/licenses/MIT).
- Within a created `.github/` folder:
  - Add a CONTRIBUTING.md. This [CONTRIBUTING.md Gist](https://gist.githubusercontent.com/PurpleBooth/b24679402957c63ec426/raw/5c4f62c1e50c1e6654e76e873aba3df2b0cdeea2/Good-CONTRIBUTING.md-template.md) from [Billie Thompson](https://github.com/PurpleBooth) can be copied/updated.
  - Add an ISSUE_TEMPLATE.md. This [ISSUE_TEMPLATE.md](https://raw.githubusercontent.com/stevemao/github-issue-templates/master/simple/ISSUE_TEMPLATE.md) from [Steve Mao](https://github.com/stevemao) can be copied/updated.
  - Add a PULL_REQUEST_TEMPLATE.md This [PULL_REQUEST_TEMPLATE.md](https://raw.githubusercontent.com/stevemao/github-issue-templates/master/simple/PULL_REQUEST_TEMPLATE.md) from [Steve Mao](https://github.com/stevemao) can be copied/updated.
  - * CONTRIBUTING.md, ISSUE_TEMPLATE.md, and PULL_REQUEST_TEMPLATE.md will automatically be populated when issues or pull requests are submitted.

## Documentation

Documentation? I say "YES" always! There is debate around how to document and documentation best practices. Books like [Clean Code](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882) provide a lot of thoughts on documents and code comments. I find documentation to be valuable because it can provide context beyond code. Even a comment that is not updated after the code has been updated provides context when integrated within git. There are great points that disagree with my _feelings_ on documentation but my general sentiment for this talk is _anything that prevents/helps with non-manual work giving developers more opportunity to work. In the case of a well commented and documented repository, there will be less continual slack or personal conversation about the repository's code.
