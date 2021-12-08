# Zigma360 team git workflow

---

## General Rules

We use a similar strategy to the [GitLab Workflow](http://help.zigma360.com/Development/#.gitlab_workflow).

Web access to the Zigma360 Git Bitbucket server: [https://git.zigma360.com/dashboard](https://git.zigma360.com/dashboard)

The repository has the **master branch** for the main development, branches for each release with a minor version (**2-93-stable**, **2-94-stable**) and branches for **tasks** `feature/My-task-name` or **bugs** `bug/An-annoying-bug`.

Any significant change to the code (more than 1 hour) should start with an issue (task or bug) in the tracking system where the goal is described.

!!! note

	Issue titles should describe the desired state of the system, e.g. "**As an administrator I want to remove users without receiving an error**" instead of "**Admin can't remove users**".

- Every task or bug have to be done on a separate **feature branch** and the name of this branch should start with the issue number,
  for example "**SWF-00101-add-some-buttons**".
- When you are done or want to discuss the code you open a **merge/pull request**. This is an online place to discuss the change and review the code. Opening a merge/pull request is a manual action since you do not always want to merge a new branch you push, it could be a long-running environment or release branch. If you open the merge request but do not assign it to anyone it is a 'Work In Progress' merge request.
- When you feel comfortable with your branch to be merged with the master branch you assign it to the person that knows most about the codebase you are changing and mention any other people you would like feedback from. There is room for more feedback and after the assigned person feels comfortable with the result the branch is merged. If the assigned person does not feel comfortable they can close the merge request without merging.

There are some **brunch types** if it's a feature, bug or quick fix: **Bugfix**, **Feature**, **Hotfix**, **Custom** and **Release** (when a new version is preparing).
Developers have to specify which type of brunch they use for a creating branch.
This can be done in the git web interface Bitbucket or directly from a bug tracking system like Jira
![img](http://help.zigma360.com/Development/images/Git/Create_brunch.png)

## Getting Started

### Checkout

Checkout the master branch from the repository (the very beginning)

Use this url to the Zigma360 repository:

```
https://username@git.zigma360.com/scm/zig/zigma360.git
```

it's good to specify this option to do always **rebase after pull** instead of merge (the same as command *git pull --rebase*):
`git config --global pull.rebase true`


![img](http://help.zigma360.com/Development/images/Git/Git_clone_1.png)

![img](http://help.zigma360.com/Development/images/Git/Git_clone_2.png)

![img](http://help.zigma360.com/Development/images/Git/Git_clone_3.png)

![img](http://help.zigma360.com/Development/images/Git/Git_clone_4.png)

Wait until the work has been successfully done


### Pulling

Update your local repository to the newest commits (**git pull**) - safe operation

![img](http://help.zigma360.com/Development/images/Git/Git_pull.png)

 

Update your local repository to the newest commits and undo all local changes (**git fetch**)

![img](http://help.zigma360.com/Development/images/Git/Git_fetch.png)

 
### Check for modifications

To check changes in a repository you can do from this context menu

![img](http://help.zigma360.com/Development/images/Git/Git_check_changes1.png)

![img](http://help.zigma360.com/Development/images/Git/Git_check_changes2.png)

 
### Commiting

Commit changes and push to the server at the same time

![img](http://help.zigma360.com/Development/images/Git/Git_comit1.png)

![img](http://help.zigma360.com/Development/images/Git/Git_comit2.png)

If you have forgotten to add some files to the last commit you can add them using a next one with the option "**Amend Last Commit**".
