# mvn-release-example

This projects shows the use of git flow and the gitflow-maven-plugin 
https://github.com/aleksandr-m/gitflow-maven-plugin

- start a feature-branch - `mvn gitflow:feature-start`
- publish a feature-branch - `git flow feature publish <BRANCHNAME>`
- finish a feature - `mvn gitflow:finish-feature`
- start a release - `mvn gitflow:release-start`
- publish a release - `git flow release publish <BRANCHNAME>`
- finish a release - `mvn gitflow:release-finish`
