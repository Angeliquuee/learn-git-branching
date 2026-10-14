
## Staging Area

A commit represents changes to a set of files, but there's actually a bit of process in choosing *which* file changes become *which* commits.

Git doesn't want to automatically include all change files in all commits -- that would be bad! Especially, if you have an API key that could leak into Github as part of your commit history.

Before a change to a file becomes part of commit, it has to be specifically selected. 

Git has three zones for this:

1. You Working Directory (where you edit)
2. The Staging Area (a loading dock for what is in the next commit)
3. Repository (your permanent history)

You pick *exactly* what rides along in each commit with `git add`. That's how commits stay tidy, and you're never forced to cmmit eerything at once.

Run `git status` any time to see where things stand. Right now it shows only two files you've edited but haven't staged:

```
Changes not staged for commit:
modified: app.js
modified: styles.css
```

Stage a single file with `git add app.js` or grab everything at once with `git add .`. once a file is staged, `git commit` seals it into a snapshot.

> ![Static Badge](https://img.shields.io/badge/Note-red)  Got files you never want to commit? Like the API keys, secrets, logs, or build junk? List them in a `.gitignore` file and git will quietly leave them alone.

