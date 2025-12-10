---
description: Commit changes and push
argument-hint: FILES=<paths> BRANCH=<branch>
---

Commit $FILES to $BRANCH with a detailed commit message, then push the branch.

If $FILES is not specified, commit all pending changes in the repo.

If $BRANCH is not specified, use the current branch; otherwise check out $BRANCH before committing and pushing.

