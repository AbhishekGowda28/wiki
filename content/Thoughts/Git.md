---
publish: true
created: 2026-05-19T13:55:12.135+05:30
modified: 2026-05-24T22:18:31.706+05:30
---

# git

## Git - Author & Commit

> what the difference is between _author_ and _committer_?
> The _author_ is the person who originally wrote the patch, whereas the _committer_ is the person who last applied the patch. So, if you send in a patch to a project and one of the core members applies the patch, both of you get credit — you as the author and the core member as the committer.

## Branch's

Commands to know the branch

| Where  | command             |
| ------ | ------------------- |
| local  | git branch --list   |
| remote | git branch --remote |
| both   | git branch --all    |

## Git hooks

Git hooks can be found in ./git/hooks folder. There we will find sample hook files, we can reuse them or create one with proper names.

Example of using git hook: Using `commit-msg` hook

1. Go to hooks folder and create a hook
   ```bash
   cd ./git/hooks
   cp commit-msg.sample commit-msg
   ```

Since the `.git` folder is excluded from the commit tree, we can create a `git-template` folder and add our `hooks`&`info` in there.

---

references

- [git hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)
- [Atlassian - git hooks](https://www.atlassian.com/git/tutorials/git-hooks)
- [How to create a git template directory-folder](https://devtutorial.io/how-to-create-a-git-directory-template-p1250.html)
- [git-bisect - Use binary search to find the commit that introduced a bug](https://git-scm.com/docs/git-bisect)
