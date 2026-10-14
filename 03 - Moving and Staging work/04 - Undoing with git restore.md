## Undoing with `git restore`

Everybody makes a little mess sometimes. You stage a file you didn't mean to, or start an experiment you'd rather throw away. `git restore` is the modern, purpose-built undo button for your working directory and staging area. 

It comes in two flavors:

* `git restore --stage <file>:` **unstage** a file (move it back out of the staging area, keeping your edits)

* `git restore <file>:` **discard** your edits to a file entirely (careful, this throws the changes away!)

> These replace the older `git reset HEAD <file>` and `git checkout -- <file> tricks. Same idea, much clearer names.`

### Here's the mess on your desk right now:

```
Changes to be committed:
modified: app.js
modified: secret.env
Changes not staged for commit: modified: experiment.js
```

You want to commit `app.js`, but `secret.env` got staged early by accident (it should be a commit on top). Also the `experiment.js` changes did not work so lets throw that out entirely.


## Tidy up, then commit

* Unstage the secret: `git restore --staged secret.env`
* Discard the experiment: `git restore experiment.js`
* Commit what's left: `git commit`

<p align="center"> <img src="../Images/37.png"> </p>
