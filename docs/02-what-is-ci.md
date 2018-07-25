# Continuous Integration

Continuous Integration is the practice of merging all developer working copies to a shared mainline several times a day. [Read more here](https://en.wikipedia.org/wiki/Continuous_integration).

----

## My definition

> Continuous Integration is a pattern of programming combining testing, safety checks, and development practices to confidently push code from a development branch to production ready branch continuously.

----

> The definition that I provided includes continuous delivery (CD). CD is not focused in this talk. CD is process of continuously delivering code to production. Although CD is not included in this talk, if CI is done well, it is a great benefit to continuously deliver new code to production. This is why CI/CD is an acronym that developers see often.

----

## What are the main parts of CI within a repository?

This talk further explains CI in 4 repository parts: code, a feedback loop for discussing code, testing code, runner scripts that compile production quality code and run testing code.

Listed below are brief descriptions of the 4 parts of a repository as they pertain to CI.

- **Code**
  - Code can exist in many environments—think FTP, code editor tools, design tools (After Effects)—if your mind immediately jumps to git. Git repositories are a standard environment to store code. This talk focuses on code hosted on Github and is updated using git and published via NPM. CI incorporates runner scripts and testing code to review code.
- **Feedback Loop**
  - The Feedback loop is how other developers discuss, share, and update code—even if they never talk. This does not initially appear to be part of CI. However, for CI to be maintainable, common feedback loop patterns should be established. This can be done with linting, editor configuration, types, comments, documentation and auto templates during the integration process. Examples of code that provides a feedback loop are linters ([Eslint](https://eslint.org/)), comments ([JSDoc](http://usejsdoc.org/)), and [Github templates](https://help.github.com/articles/about-issue-and-pull-request-templates/). CI uses runner scripts and Github to provide developers with a feedback loop.
- **Testing code**
  - Unit tests, acceptance tests, linting, and types provide information about code quality. These bits of code (or scripts) define whether the quality is mergable into a production branch—before another developer even looks at any code changes! These bits of code do not exist in production. Examples of testing code are unit testing libraries ([Jest](https://jestjs.io/)) and linters (Eslint, [write-good](https://github.com/btford/write-good)). CI uses runner scripts to run testing code.
- **Runner Scripts**
  - While Testing code defines code quality. Testing code does not build code for production or run tests in a maintainable or chronological way. Runner Scripts run test code, compile code for production, and provide feedback loops so that engineers or systems can decide if code is production ready. Examples of runner scripts are tools like npm or [yarn's cli](https://yarnpkg.com/lang/en/docs/cli/) and [bash scripts](http://matt.might.net/articles/bash-by-example/). CI uses runner scripts to provide a feedback loop and test code.
