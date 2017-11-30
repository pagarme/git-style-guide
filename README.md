<img src="https://avatars1.githubusercontent.com/u/3846050?v=4&s=200" width="127px" height="127px" align="left"/>

# Git Style Guide

Git style guide suggested by Pagar.me. 

<br>

## Branches

  - [1.1](#) Choose short and descriptive names.
    > Identifiers from corresponding tickets in an external service (eg. a GitHub issue) are also good candidates for use in branch names.

    ```
    # good
    $ git checkout -b feature/oauth

    # good: using identifiers
    $ git checkout -b fix/issue-15

    # bad: too vague
    $ git checkout -b login_fix
    ```

  - [1.2](#) Use dashes to separate words.

    ```sh
    # good
    $ git checkout -b feature/add-webhook

    # bad
    $ git checkout -b feature/add_webhook
    ```

## Commits JASIUAIUSAIUSUIA

  - [2.1](#) Each commit should represent a single logical change.
    > Don't make several logical changes in one commit. For example, if a patch fixes a bug and optimizes the performance of a feature, split it into two separate commits.

    > **Tip:** Use git add -p to interactively stage specific portions of the modified files.

  - [2.2](#) Don't split a single logical change into several commits.
    > For example, the implementation of a feature and the corresponding tests should be in the same commit.

  - [2.3](#) Commit early and often.
    > Small, self-contained commits are easier to understand and revert when something goes wrong.

    > **Tip:** Use git add -p to interactively stage specific portions of the modified files.

  - [2.4](#) Commits should be logically sorted.
    > If commit X depends on changes done in commit Y, then commit Y should come before commit X. Similarly, if commit A solves a bug introduced by commit B, it should also be stated in the message of commit A.


  - [2.5](#) NEVER let a commit break any working functionality.
    > ALWAYS guarantee that the master branch only contains commits that are fully functional, have their own tests and fixes.

    > **Note:** While working alone on a local branch that has not yet been pushed, it's fine to use commits as temporary snapshots of your work. However, it still holds true that you should apply all of the above before pushing it to remote. To do that it's really important to understand `git rebase -i`.

## Messages

  - [3.1](#) Use the editor, not the terminal, when writing a commit message.
    > **Why?** Committing from the terminal encourages a mindset of having to fit everything in a single line which usually results in non-informative, ambiguous commit messages.

    ```sh
    # good
    $ git commit

    # bad: no commit message
    $ git commit -m "Quick fix"
    ```

  - [3.2](#) A commit message consists of three distinct parts separated by a blank line: the title, an optional body and an optional footer. The layout looks like this:

    ```
    context: subject

    body

    footer
    ```

    - **Title:** consists of the context of the message and subject.
    - **Context:** the part of the of the application that is being changed.
    - **Subject:** what is being changed. Subjects should be no greater than 50 characters, should begin with a capital letter and do not end with a period. Use an imperative tone to describe what a commit does, rather than what it did. For example, use change; not changed or changes.
    - **Body:** use the body to explain the what and why of a commit, not the how. When writing a body, the blank line between the title and the body is required and you should limit the length of each line to no more than 72 characters. Ultimately, when writing a commit message, think about what you would need to know if you run across the commit in a year from now.
    - **Footer:** the footer is optional and is used to reference issue tracker IDs.

    Example commit message:

    ```
    core: Summarize changes in around 50 characters or less

    More detailed explanatory text, if necessary. Wrap it to about 72
    characters or so. In some contexts, the first line is treated as the
    subject of the commit and the rest of the text as the body. The
    blank line separating the summary from the body is critical (unless
    you omit the body entirely); various tools like `log`, `shortlog`
    and `rebase` can get confused if you run the two together.

    Explain the problem that this commit is solving. Focus on why you
    are making this change as opposed to how (the code explains that).
    Are there side effects or other unintuitive consequenses of this
    change? Here's the place to explain them.

    Further paragraphs come after blank lines.

     - Bullet points are okay, too

     - Typically a hyphen or asterisk is used for the bullet, preceded
       by a single space, with blank lines in between, but conventions
       vary here

    If you use an issue tracker, put references to them at the bottom,
    like this:

    Resolves: #123
    See also: #456, #789
    ```

## Merging

  - [4.1](#) Do not rewrite published history.
    > **Why?** The repository's history is valuable in its own right and it is very important to be able to tell what actually happened.

    Altering published history is a common source of problems for anyone working on the project. However, there are cases where rewriting history is legitimate. These are when:
    - You are the only one working on the branch and it is not being reviewed.
    - You want to tidy up your branch (eg. squash commits) and/or rebase it onto the "master" in order to merge it later.

  - [4.2](#) Keep the history clean and simple.
    > Make sure it conforms to the style guide and perform any needed actions if it doesn't (squash/reorder commits, reword messages etc.).

  - [4.3](#) Rebase it onto the branch it's going to be merged to.
    > **Note:** This strategy is better suited for projects with short-running branches. Otherwise it might be better to occasionally merge the "master" branch instead of rebasing onto it.

  - [4.4](#) NEVER commit something like "Fix linter" or "Fix tests".
    > **Why?** These "fixes" should be squashed to the commits that originated the change.

  - [4.5](#) NEVER fully squash a branch before merging it.

  - [4.6](#) NEVER use  git merge master on a branch.
    > ALWAYS use git rebase master, then force-push, wait for the CI to clear and only then merge into master.

## Need Help ?

If you are not familiar with git commands or need help to accomplish the style guide, check [k88hudson/git-flight-rules](https://github.com/k88hudson/git-flight-rules) for some usage tips and walkthrough.
