---
description: Generates a pull request in Github for the current changes.
argument-hint: [DEV_BRANCH=<dev_branch>] [TARGET_BRANCH=<target_branch>]
---

Commit the current changes to $DEV_BRANCH with a detailed commit message. If $DEV_BRANCH is not specified, commit to dev unless $TARGET_BRANCH is dev, then create a feature branch for the changes.
Use gh to generate a PR for the changes to be submitted to $TARGET_BRANCH. If $TARGET_BRANCH is not specified, use the main branch (or master if main is not an active branch).



