# Getting started with Git & Github
The repository has been created for the session on Git & Github to have hands-on practice of the learnt concepts.
> Use the readme as a basic guide towards your first contribution! 

## Follow Us:
Github: [innogeeks](https://github.com/innogeeks)

## Getting Started

1. Go to [Getting-started-with-git-github-2021]https://github.com/InnogeeksOrganization/Getting-started-with-git-github-2021) repository
2. Click on the Fork button in the upper right corner.

Introduce your self to GIT, make sure you use an email associated with your GitHub account.
```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

Make sure you clone the forked repository.
```
git clone https://github.com/<your username>/Getting-started-with-git-github-2021.git
```

Switch Getting-started-with-git-github-2021 to your fork
```
git remote set-url origin https://github.com/<your username>/Getting-started-with-git-github-2021.git
```

Setup Getting-started-with-git-github-2021 to be able to fetch from the master
```
git remote add upstream https://github.com/InnogeeksOrganization/Getting-started-with-git-github-2021.git
```

## Adding Features

When you add a new feature always create an issue first, this allows others to comment and give you tips. It will also help us keep track of what people are adding and with new releases helps us to write new release notes and give you credit for your work.

Secondly, always work in a branch, never work on the master branch. Keep your master branch in sync with the master of the official Getting-started-with-git-github-2021 repository. This makes the pull requests (you do want your work to be in the main branch right?) easier for us.

Finally, try to keep your branches focused on fixing/adding only one feature and try not to fall in the trap of doing a lot of things in a single branch. This will not only make it harder for us to process your pull request but makes it take longer before you can submit your pull request. Small pull requests are more likely to be looked at faster and pulled into the main branch faster.

Here is a simplified workflow on how to add a new feature:


#### Alternative

`git fetch` only downloads the changes from the upstream and doesn't integrate those into your forked repository. You have to use an additional command `git merge` to do so. Alternatively, `git pull` not only downloads the changes but also integrate those into your forked repository.

Set up  the original repository as your upstream.
```
git remote add upstream https://github.com/InnogeeksOrganization/Getting-started-with-git-github-2021.git
```
Now, fetch and merge the changes from the original repository simultaneously.
```
git pull upstream master
```
Update your forked Github repository.
```
git push origin master
```

To summarize, see the section below.


### Get latest version

Update your master (both locally and on GitHub)

```
git fetch upstream
git checkout master
git merge upstream/master
git push
```


### Git Merge VS Git Rebase

Rebasing and merging are both used for integrating changes from one branch into another—but they do it in different ways.

Instead of 
```
git merge upstream/master
```
you can also use
```
git rebase upstream/master
```


#### The Merge Option

`git merge` will integrate the histories of the upstream branch and your master branch, giving you a branch structure that looks like:

![IMAGE](https://wac-cdn.atlassian.com/dam/jcr:e229fef6-2c2f-4a4f-b270-e1e1baa94055/02.svg?cdnVersion=1060)

Merging preserves history since, the existing branches are not changed in any way.Merging adds a new commit to the history. 


#### The Rebase Option

`git rebase` will move the entire upstream branch on the tip of your master branch, giving you a branch structure that looks like:

![IMAGE](https://wac-cdn.atlassian.com/dam/jcr:5b153a22-38be-40d0-aec8-5f2fffc771e5/03.svg?cdnVersion=1060)

Rebasing re-writes the history by creating brand new commits for each commit in the original branch.


#### Which command to prefer?

`git rebase` is usually preferred over `git merge` because
>- It results in a perfectly linear and readable history.
>- It eliminates the unnecessary merge commits required by git merge. 
>- It can remove undesired commits or squash two or more commits into one.


### Create a branch to do your work.

A good practice is to call the branch in the form of GH-<issue-number> followed by the title of the issue. This makes it easier to find out the issue you are trying to solve and helps us to understand what is done in the branch. Calling a branch my-work is confusing. Names of a branch can not have a space, and should be replaced with a hyphen.

```
git checkout -b GH-issuenumber-title-of-issue
```

### Work and commit

Do you work, and commit as you see fit. Make your commit messages helpful.

In general commit messages follow these guidelines 

```
A brief commit message in one or two lines
```
**Followed By**

```
Detailed explanation of your commit 

eg : If this commit fixes a bug in the code then describe the bug, what was causing it, your solution or 
any other relevant thing one should know if someone else works on this project.
```
See this [commit format](https://commit.style/)

You can also refer this [article](https://medium.com/@steveamaza/how-to-write-a-proper-git-commit-message-e028865e5791) on how to write commit messages. 


### Git Squash

To `squash` means commonly to compact multiple commits into one to make it more concise, readable and not to pollute main branch’s history. To achieve that, interactive mode of `git rebase` command used.
To squash the last n commits into one, run the following command:

```
git rebase -i HEAD~n
```

That will open up a text-editor with something similar to the following:

```
pick commit_1
pick commit_2
pick commit_3
...
pick commit_n
# Bunch of comments
```

Leave the first commit alone, and change the rest of the `pick` to `squash` or `s`.

```
pick commit_1
squash commit_2
squash commit_3
...
squash commit_n
# Bunch of comments
```

Save and exit the editor. Now, the editor will reopen right away suggesting to reword commit messages. Make the changes if you want. The commit message will include all the lines that are not starting with `#` character. Once again, save and exit the editor.
Your terminal now would show a success message including `Successfully rebased and updated <branch name>` and the `git log` would show a compacted history with only one commit.


### Push your changes up to GitHub.

If this is the first time pushing to GitHub you will need to extended command, otherwise, you can simply do a `git push`.

```
git push -u origin GH-issuenumber-title-of-issue
```


### Pull Request

- When finished create a pull request from your branch to the main Getting-started-with-git-github-2021 repository.

- When making a pull request use `Closes #(issue_number)` in the description of your PR, so that GitHub automatically associates your PR with that issue.

- In the description of your PR, mention what bug or feature this provides. Give any relevant information, that you think maintainer should know like :

 - Tests you did to check your new PR or code
 - Your approach to the problem
 - Any other relevant information that you think one might keep in mind for future

Make it clear,complete and simple so your PR gets merged easily !

Refer this [Git Fork and Pull Request Cheat Sheet](https://help.github.com/en/articles/about-pull-request-merges)


### Code Review 

- You can also help the community by reviewing other people's PR, this is known as **code review**

- Go to a PR, then **Files Changed** section, review the code and mark the file as reviewed

- You can also use GitHub's WebUI to add comments and provide some suggestions for PR's author.

Refer this [link](https://medium.com/osedea/the-perfect-code-review-process-845e6ba5c31) to know about **Code Reviews** and its importance. 


### Using GitHub UI :

GitHub provides a Web UI to make communication process easier

- You can use `@(account_name)` to mention someone

- Mentioning Pull Requests or issues using `#(issue_id)`, Read [this](https://help.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue)

- Also, take a look at [this](https://guides.github.com/features/mastering-markdown/), **Markdown or styling** your messages to increase readibilty for PR description and conversations.