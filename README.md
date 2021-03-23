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
    * Checking for uncommitted changes.
    * Fetching remote branch 'origin develop'.
    * Comparing local branch 'develop' with remote 'origin/develop'.
    * Checking out 'develop' branch.
    * Checking for SNAPSHOT versions in dependencies.
    * prompt for release versions
    * Creating a new branch 'release/<RELEASEVERSION>' from 'develop' and checking it out.
    * Updating version(s) to '<RELEASEVERSION>'.
    * Committing changes.
    * Pushing 'release/<RELEASEVERSION>' branch to remote.
- finish a release - `mvn gitflow:release-finish`
    *  Checking for uncommitted changes.
    *  Checking out 'release/<RELEASEVERSION>' branch.
    *  Checking for SNAPSHOT versions in dependencies.
    *  Fetching remote branch 'origin release/<RELEASEVERSION>'.
    *  Comparing local branch 'release/<RELEASEVERSION>' with remote 'origin/release/<RELEASEVERSION>'.
    *  Fetching remote branch 'origin develop'.
    *  Comparing local branch 'develop' with remote 'origin/develop'.
    *  Fetching remote branch 'origin master'.
    *  Comparing local branch 'master' with remote 'origin/master'.
    *  Checking out 'release/<RELEASEVERSION>' branch.
    *  Cleaning and testing the project.
    *  Running Maven goals: verify
    *  Checking out 'master' branch.
    *  Merging (--no-ff) 'release/<RELEASEVERSION>' branch.
    *  Creating '<RELEASEVERSION>' tag.
    *  Checking out 'develop' branch.
    *  Merging (--no-ff) 'release/<RELEASEVERSION>' branch.
    *  Updating version(s) to '<SNAPSHOTVERSION>'.
    *  Committing changes.
    *  Pushing 'master' branch to 'origin'.
    *  Pushing 'develop' branch to 'origin'.
    *  Deleting remote branch 'release/<RELEASEVERSION>' from 'origin'.
    *  Deleting 'release/<RELEASEVERSION>' branch.

there are also goals for hotfix and support branches
