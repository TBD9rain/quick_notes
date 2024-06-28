# Introduction

**Tips for Project Management**


# Semantic Versioning

X.Y.Z

X is the **major** version, corresponding to solution changes.

Y is the **minor** version, corresponding to functionality changes.

Z is the **patch** version, corresponding to bug fixing and other codes changes.

Referenced from [Semantic Versioning](https://semver.org/).


# README

README shall consist of version summary and overview of current version.


# Git Specification

Atomic commit should be the first choice for version and file management with Git.
Atomic commit signifies that a commit should be the smallest complete unit of change.

`git rebase` should be considered when facing git error correcting or similar issues.
Project error should be fixed with another commit with corresponding messages.


## Git Message Format

Git message format is referenced from
[Conventional Commits](https://github.com/conventional-commits/conventionalcommits.org/blob/master/content/v1.0.0/index.md)
and [angular](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines).

```
<type>[(<scope>)][!]: <description>

[<body>]

[<footer>]
```

`<type>` must be one of following:
- chore, changes not directly affect main design
- docs, changes of documentations
- feat, changes for a new feature
- fix, changes to fix a bug
- perf, changes to improve performance
- refactor, changes of codes structure not affecting functions
- revert, revert changes with `git revert`
- style, changes about formatting code style
- test, changes of verification or validation

For example, in FPGA development `<scope>` could be:
- alg, algorithm
- fxp, fixed-point modeling
- rtl, register transmission level
- onb, onboard
- ...

Optional `!` could be used to mark significant changes.

`<description>` must contain succinct description of the change.
Use lowercase words, imperative tense, and no dot `.` at the end.

Optional `<body>` could include the motivation for the change and more details about the change.

Optional `<footer>` could contain other information about siginificant changes,
such as corresponding issues etc.


# Project File Management Structure


## FPGA development

- \<pj\_name\>

    - algorithm
    - fixed_point
    - data
    - docs
    - refs
    - fpga
        - \<eda\_project\>
        - sim
            - \<module_name\>
                - [testcase]
                - [auto]
            - ...
        - src
        - tb
            - \<module_name\>
            - ...
        - \<others\>
    - \<others\>

