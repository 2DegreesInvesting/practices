These practices:

* are aspirational but when they can't be followed it's nice to explain why;
* document heuristics, as detailed instructions may never cover all scenarios;
* apply to shared commits (maybe after cleaning commits locally).

## tl;dr

* Shared commits[^shared_commit] should not be changed.
* Changes in each shared commit should be closely related.

[^shared_commit]: A _shared_ commit is a commit that someone other than you
might access, for example, because you pushed it to a remote repository that
someone else has permission privileges to access.

## 1. Preserve shared history

Shared commits should never change. Some Git commands preserve the history, but
others don't. For example, `git commit --amend` and `git rebase --interactive`
alter the git history; they help to overwrite  a messy commit history with
a cleaner one; you should use them only before sharing your work. To cleanup
shared history use instead `git revert`.  If you try to push altered history by
accident, Git will stop you; to benefit from this protection  avoid `--force`
(or `-f`) when pushing to shared repositories.

See also:

* [Cleaning _unshared_ history: Squashing all commits in a branch](https://youtu.be/08dhy3Zoob4).
* [Cleaning _unshared_ history with `git rebase --interactive`](https://youtu.be/cMI8p1XhMzA).
* [Cleaning _unshared_ history with `git commit --amend`](https://youtu.be/539pfVfr7OI).
* [Cleaning shared history with `git revert`](https://youtu.be/A8Ld6iDqc3w).
* [Git playlist](https://www.youtube.com/playlist?list=PLvgdJdJDL-AOHkwiaMvYhPKVjiD9vzZIo).

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
* Undoing things with Git ([video](https://youtu.be/dZOfEF19yDk),
[lesson](https://coderefinery.github.io/git-intro/05-undoing)).

## 3. Commit frequently

Committing frequently keeps your commits small. Small commits are more likely
to be focused; they are easier to review, and easier to merge because they
offer fewer opportunities for conflicts.

## 4. The work you share should be complete

Each commit and feature should do what it promises, completely; and reverting
it should undo what that commit or feature meant to do, also completely. If
the goal of one commit requires changes in two files, that one commit should
include changes to both files. Similarly, if the goal of a feature requires
two kinds of changes, that feature should likely include two commits.

## 5. Explain how to test the effect of the changes you made

Testing your code is important, particularly when sharing it with
others. Automated tests are the best but not the only way to test the effects
of the changes you made. When automated tests are excluded, the PR's first
comment should explain how you ensured that the code behaves as you expect,
and how someone else may reproduce your results.

## 6. Structure each commit message like an email

Like an email, commit messages have a subject and an optional body. The subject
should start with a line summarizing your changes (aim for 50 characters or
less). Use the imperative, present tense -- for example, "Fix typo",
not "Fixed typo" or "Fixes typo". The message body, if present,
should follow a blank line; wrap around 70 characters; and explain the
motivation for the change ("why", not "what" or "how").

See also:

* [Example of a commit message](https://github.com/2DegreesInvesting/resources/issues/74).
* [Commit best practices](https://r-pkgs.org/git.html#commit-best-practices).

## 7. Agree on a workflow

Choose a workflow based on your team's needs and preferences. However you
choose to work, just make sure to agree on a common workflow that everyone
follows:

GitHub workflow:

This workflow is 2DII's default. If a project uses a different
workflow, document prominently (e.g. in README) what that workflow is
([example](https://github.com/github/gitignore#contributing-workflow)).

* Uses a central repository. 
* Uses a single long-lived branch: "main"; it never contains broken code.
* Developers work on "feature" branches (never on the "main" branch), share
them via pull requests, and peers review the changes before they become a
part of the main codebase.
* A new release is created by tagging a particular commit on the main branch.

Gitflow workflow:

* Like the GitHub workflow but uses two long-lived branches: "main"
and "develop". The main branch stores the official release history,
and the develop branch serves as an integration branch for features.

A team may agree on custom conventions beyond the "vanilla" workflows listed
above.  For example, you may agree to prefix a commit-title with "FIXME",
"Amend: " or to whatever to communicate with your team succinctly via a
vocabulary you all share.

See also: 

* [Comparing workflows](https://www.atlassian.com/git/tutorials/comparing-workflows).

## 8. Use tools to be more productive

Choose the tools that help you work more comfortably, more productively,
and with fewer errors.

See also:

* [Install a Git client](https://happygitwithr.com/git-client.html)
* [oh-my-zsh: Unleash your terminal like never before](https://ohmyz.sh/).
* [gh: Take GitHub to the command line](https://cli.github.com/).
* [Git from RStudio](https://rstudio.com/resources/webinars/managing-part-2-github-and-rstudio/).

## References

[Version control best practices](https://www.git-tower.com/blog/version-control-best-practices/)

## How

* [Git practices by example](TODO)
* [Coding helpdesk](https://github.com/2DegreesInvesting/coding-helpdesk#coding-helpdesk).
* [GitHub's Git guides](https://github.com/git-guides/).
* [Coderefinery's Git intro](https://coderefinery.github.io/git-intro/).
* [Git best practices](https://bit.ly/book-git-in-practice).  
* [Visualization of useful Git commands](https://dev.to/lydiahallie/cs-visualized-useful-git-commands-37p1).


