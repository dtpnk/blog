---
title: "GIT - Create a new Branch with no history
"
excerpt_separator: "<!--more-->"
categories:
  - EN
tags:
  - git
  - CLI
---


this creates a `<NEW_BRANCH_NAME>` from the current branch, with the last commit as the only commit. (no history)

```
git branch <NEW_BRANCH_NAME> $(echo "init commit" | git commit-tree HEAD^{tree})
```



