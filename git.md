These practices:

* are aspirational but when they can't be followed it's nice to explain
* are aspirational but when they can't be followed it's nice to explain
* are aspirational but when they can't be followed it's nice to explain
* are aspirational but when they can't be followed it's nice to explain
why;
* document heuristics, as detailed instructions may never cover all scenarios;
* apply to shared commits (maybe after cleaning commits locally).

## tl;dr

* Shared commits should not be changed.  * Changes in each shared commit
should be closely related.

## 1. Preserve shared history

Shared commits should never change. Some Git commands preserve the history, but
others don't. For example, git commit --amend and git rebase --interactive
alter the git history; they help to overwrite  a messy commit history with
a cleaner one; you should use them only before sharing your work. To cleanup
shared history use instead git revert.  If you try to push altered history by
accident, Git will stop you; to benefit from this protection  never --force
push to shared repositories.

## 2. Keep commits focused

A commit should focus on related changes only. For example, fixing two
different bugs should produce two separate commits. Small commits make it
easier for other developers to understand the changes and roll them back if
something went wrong. You can avoid sharing unwanted changes via .gitignore. If
you can't succinctly describe what the commit is doing in a couple of words,
then it is likely too big.

See also:

* [The right size of a PR](https://github.com/2DegreesInvesting/practices/discussions/3).
* [.gitignore templates](https://github.com/github/gitignore).

TODO: Undoing things with Git

## 3. Commit frequently

Committing frequently keeps your commits small. Small commits are more likely
to be focused; they are easier to review, and easier to merge because they
offer fewer opportunities for conflicts.

## 4. The work you share should be complete

Each commit and feature should do what it promises, completely; and reverting
it should undo what that commit or feature meant to do, also completely. If
the goal of one commit requires changes in two files, that one commit should
include changes to both files. Similarly, if the goal of a feature requires
two kinds of changes, that feature should likely include two commits.  TODO:
Undoing things with Git

## 5. Explain how to test the effect of the changes you made

Testing your code is important, particularly when sharing it with
others. Automated tests are the best but not the only way to test the effects
of the changes you made. However you did it, explain how you ensured that the
code behaves as you expect, and how someone else may reproduce your results.

## 6. Structure each commit message like an email

Like an email, commit messages have a subject and an optional body. The subject
should start with a line summarizing your changes (aim for 50 characters or
less). Use the imperative, present tense -- for example, “Fix typo”,
not “Fixed typo” or “Fixes typo”. The message body, if present,
should follow a blank line; wrap around 70 characters; and explain the
motivation for the change (“why”, not “what” or “how”).

See also:

* [Example of a commit message](https://github.com/2DegreesInvesting/resources/issues/74).
* <https://r-pkgs.org/git.html#commit-best-practices.>

## 7. Agree on a workflow

Choose a workflow based on your team's needs and preferences. However you
choose to work, just make sure to agree on a common workflow that everyone
follows:

GitHub workflow (a.k.a Git feature branch workflow:

* Uses a central repository. 
* Uses a single long-lived branch: “main”; it never contains broken code.
* Developers work on "feature branches, share them via pull requests, and
peers review the changes before they become a part of the main codebase.
* A new release is created by tagging a particular commit on the main branch.

Gitflow workflow:

* Like the GitHub workflow but uses two long-lived branches: “main”
and “develop”. The main branch stores the official release history,
and the develop branch serves as an integration branch for features.

See also: <https://www.atlassian.com/git/tutorials/comparing-workflows>.

## 8. Use tools to be more productive

Choose the tools that help you work more comfortably, more productively,
and with fewer errors.

TODO: Share links to tools:

* CLI git 
* CLI gh 
* RStudio git pane 
* GitKraken 
* GitHub Client

## References

[Version control best practices](https://www.git-tower.com/blog/version-control-best-practices/)

## How

* [Git practices by example](TODO)
* <https://github.com/2DegreesInvesting/coding-helpdesk#coding-helpdesk>.
* <https://github.com/git-guides/>.
* <https://coderefinery.github.io/git-intro/>.
* <https://bit.ly/book-git-in-practice (Part 4: Git best practices)>.  
* <https://dev.to/lydiahallie/cs-visualized-useful-git-commands-37p1>.

## Discuss

* Jackson: Always include files like LICENSE, README.md, and consider
.gitignore and CONTRIBUTING.md.  
* Taylor: Develop a consensus for types of
changes, e.g. “amend” (something I thought I had already done).  
* CJ: Don't ever commit to master/ main, even locally.

