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
    * Creating a new branch 'release/&lt;RELEASEVERSION&gt;' from 'develop' and checking it out.
    * Updating version(s) to '&lt;RELEASEVERSION&gt;'.
    * Committing changes.
    * Pushing 'release/&lt;RELEASEVERSION&gt;' branch to remote.
- finish a release - `mvn gitflow:release-finish`
    *  Checking for uncommitted changes.
    *  Checking out 'release/&lt;RELEASEVERSION&gt;' branch.
    *  Checking for SNAPSHOT versions in dependencies.
    *  Fetching remote branch 'origin release/&lt;RELEASEVERSION&gt;'.
    *  Comparing local branch 'release/&lt;RELEASEVERSION&gt;' with remote 'origin/release/&lt;RELEASEVERSION&gt;'.
    *  Fetching remote branch 'origin develop'.
    *  Comparing local branch 'develop' with remote 'origin/develop'.
    *  Fetching remote branch 'origin master'.
    *  Comparing local branch 'master' with remote 'origin/master'.
    *  Checking out 'release/&lt;RELEASEVERSION&gt;' branch.
    *  Cleaning and testing the project.
    *  Running Maven goals: verify
    *  Checking out 'master' branch.
    *  Merging (--no-ff) 'release/&lt;RELEASEVERSION&gt;' branch.
    *  Creating '&lt;RELEASEVERSION&gt;' tag.
    *  Checking out 'develop' branch.
    *  Merging (--no-ff) 'release/&lt;RELEASEVERSION&gt;' branch.
    *  Updating version(s) to '&lt;SNAPSHOTVERSION&gt;'.
    *  Committing changes.
    *  Pushing 'master' branch to 'origin'.
    *  Pushing 'develop' branch to 'origin'.
    *  Deleting remote branch 'release/&lt;RELEASEVERSION&gt;' from 'origin'.
    *  Deleting 'release/&lt;RELEASEVERSION&gt;' branch.

there are also goals for hotfix and support branches
