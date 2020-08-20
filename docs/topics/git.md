# Git

## (GT-50) Use 'main' as your primary branch

All branches must be created from the `main` branch

Rationale:

-   Multiple levels of branching from the `main` branch can create opportunities
    for merge conflicts

Exceptions:

-   None

## (GT-100) Only Branch from Main

All branches must be created from the `main` branch

Rationale:

-   Multiple levels of branching from the `main` branch can create opportunities
    for merge conflicts

Exceptions:

-   None

## (GT-200) Feature Branch Naming

Per GT-200, repositories should only contain a single `main` branch and zero
or more feature branches.

Feature branches must be named: `feature/<descriptive name>`

For example, if you're working on a feature that allows users to change the email
address in their profile, the branch should be named `feature/change-email`

Rationale:

-   Without a good naming convention, it is very easy to lose track of the purpose
    of a branch

Exceptions:

-   None

## (GT-300) Delete Merged Branches

After a branch has been merged to the `main` branch, it must be immediately deleted.

Rationale:

-   Short-lived branches are a best-practice for minimizing merge conflicts.
    Leaving many branches active in a repository makes it difficult for team members
    to navigate the ongoing work. Once a branch has been reviewed, approved, and merged
    into the `main` branch, it should be immediately deleted.
-   A healthy Git repository has a minimum of active branches.
-   This is [easy to comply with using GitHub](https://help.github.com/en/github/administering-a-repository/managing-the-automatic-deletion-of-branches).

Exceptions:

-   None
