To move your commits from the protected main branch to a new branch, follow these steps:

1. **Create a new branch from your current position** (this preserves your commits):
```bash
git branch feature-branch-name
```

2. **Reset main branch to match the remote** (removes your commits from main):
```bash
git reset --hard origin/main
```

3. **Switch to your new branch**:
```bash
git checkout feature-branch-name
```

4. **Push your new branch to remote**:
```bash
git push -u origin feature-branch-name
```

Now your commits are safely on `feature-branch-name` and you can create a pull request to merge them into main later.

**Note**: If you've already pushed to main and it was rejected, you can skip step 2's `--hard` reset since the remote main is still clean. Just create the new branch and switch to it.

**Alternative one-liner** to create and switch in one step:
```bash
git checkout -b feature-branch-name
git branch -f main origin/main
```

This moves your work to a new branch while resetting main to match the remote.
