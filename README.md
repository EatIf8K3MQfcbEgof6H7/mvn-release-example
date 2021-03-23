# mvn-release-example

This projects shows the use of git flow with the gitflow-maven-plugin 
https://github.com/aleksandr-m/gitflow-maven-plugin

- start a feature - `mvn gitflow:feature-start`
    * check for uncommited changes
    * fetches remote/develop and merge with local develop (if possible)
    * prompt for branch-name
    * creates a new local feature-branch from develop
    * adds branchname to version in pom.xml
    * commit changes

- finish a feature - `mvn gitflow:feature-finish`
    * check for uncommited changes
    * prompt for feature-branch-name to finish
    * fetches remote/feature-branch and merge with local feature-branch (if possible)
    * checkout develop and merge feature-branch into develop (if possible)
    * remove feature-branch-name from version in pom.xml
    * commit changes
    * push changes to remote/develop
    * remove feature-branch local and remote

- start a release - `mvn gitflow:release-start`
- finish a release - `mvn gitflow:release-finish`

there are also goals for hotfix and support branches
