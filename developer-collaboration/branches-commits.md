# Branches & Commits

## Branch Rules

Create a new branch whenever you start working on something. **Don't commit to `main` or `development`, as these branches are used for the production and staging environments and need to be stable.**

Branch names are up to you, but we recommend including the issue number and a brief title. You can also prefix branch names with `feature/`, `fix/`, or other categories.

```
123-fix-router-navigation
fix/router-navigation
```

### The `main` Branch

The `main` branch reflects our currently deployed production state. Most PRs should never be merged directly into `main`, but rather `development`.

We will create a new PR to merge the delta between staging and production regularly.

### The `development` Branch

Once you finish a task and create a PR for it, it should merge into development, the equivalent of a staging environment. Don't merge work that isn't done yet. Instead, if more PRs are about to follow, combine them into a feature branch.

### Feature Branches

Working on more significant issues means that a couple of PRs need to be merged first before releasing the feature to development. That's what you can use feature branches for.

Please prefix feature branches with `feature/` to make it transparent, e.g.:

```
feature/add-analytics-page
```

## Commits

We use [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/#summary) across all repositories. This means that our commit messages have a certain structure:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

The commit type can include the following:

- **feat:** a new feature is introduced with the changes
- **fix:** a bug fix has occurred
- **chore:** changes that do not relate to a fix or feature and don't modify src or test files (for example, updating dependencies)
- **refactor:** refactored code that neither fixes a bug nor adds a feature
- **docs:** updates to documentation such as a README or other markdown files
- **style:** changes that do not affect the meaning of the code, likely related to code formatting such as white space, missing semi-colons, and so on
- **test:** including new or correcting previous tests
- **perf:** performance improvements
- **ci:** continuous integration-related
- **build:** changes that affect the build system or external dependencies
- **revert:** reverts a previous commit

The commit-type subject line should be lowercase with a character limit to encourage succinct descriptions. The optional commit body should be used to provide further detail that cannot fit within the character limitations of the subject line description.

Below is an example of a conventional commit:

```
fix: remove duplicate entry in router

This fixes the problem of the navigation not working
properly and instead putting the new page at the bottom.

Closes #123
```
