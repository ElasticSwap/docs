# Issues

We offer different templates for these issue types when creating a new issue. Below is an explanation.

## Issue Types

We have three types of issues: epics, user stories, and bug reports. Generally speaking, whenever you create a new issue, it should fit in one of these categories. However, it's also okay to diverge from the structure if it doesn't fit.

### Epics

An epic is a collection of user stories used for more complex features or tasks. An epic should contain a user story describing what it is about, e.g., building a new page for the app or improving the SDK to be more performant.

Below the user story, you should list all dependencies. These are other tasks or epics inside the same or another repository required for the epic to be considered done. Using GitHub's To-Do list feature, it's easy to tick off any done task.

### User Stories

A user story can be standalone or part of an epic. Either way, its structure is always the same: write a user story at the beginning, explaining what should be built and how it affects the user. Write a user story from a user's perspective and mention the user's role (developer, trader, liquidity provider, etc.). Try to be as specific as possible but keep the language simple:

> As a trader, I want to swap elastic tokens while being aware of token decay after a rebase so that I can make the right decisions.

> As a developer, I want to have the same GraphQL API endpoints as Uniswap offers so that I can compare the total volume of a pool.

User stories are accompanied by a checklist of acceptance criteria, which is easy to do, thanks to GitHub's To-Do list feature. Below the user story, list all tasks that need to be done to achieve the stated goal. If you feel like too many items are on the acceptance criteria list, breaking up the task into more issues might make sense.

#### Dependencies

Most of the time, issues depend on each other. Say you want to implement a new page on the app:

1. First, a design needs to be created
2. Eventually, the SDK or a back end must deliver some data for you to consume
3. With the above two done, you can start working on the front end.

It's essential to make it transparent that issue 3 depends on 1 and 2, but 1 and 2 can both be started independently. Inside issue 3, write

> requires #1
> requires #2

to make that clear. Inside issues 1 and 2, write

> required by #3

### Bug Reports

Bug reports usually don't contain user stories (though they can), but it's still important to provide as many details as possible. A bad example of a bug report would be:

> Pages sometimes don't load.

With such little information, it's hard to debug what's going on. Usually, the bug reporter has more information on hand, so it's crucial to be as descriptive as possible. We have a template for bug reports, asking for detailed information such as a description, steps to reproduce, expected behavior, and screenshots to show the bug even better.

Whenever possible, try to be as specific as possible.

## Labels

We use labels to categorize issues further and make it more obvious whether an issue is a user story, bug report, or epic. So please make sure to give your issues the appropriate labels.

### Categories

- **epic:** a collection of user stories or issues towards a more extensive feature or change. Examples are a new analytics page, adding a new token, or migrating the app to another framework.
- **enhancement:** a user story or code change that improves the product. Examples are design changes, new functionality, or performance improvements.
- **bug:** a bug that a user or we have discovered. Usually, bug tickets shouldn't be too big, and if they are, there might be the need for fundamental refactoring, which leads to an epic. Examples are incorrect responsive styling, a button not doing anything upon interaction, or the back button not working.
- **documentation:** improvements or additions to our documentation. Examples are changes to markdown docs for developers (like style guides) or text changes on the website explaining the product.

### Progress

- **backlog:** use this label whenever you create a new issue and don't immediately start working on it.
- **in progress:** add this label while actively working on it. If you take a break for a couple of days, you can still leave the label, but make sure to remove it once those days turn into weeks.
- **waiting:** an issue that depends on another issue and can't be started unless all dependencies are resolved. This will happen mostly when working with epics.
- **needs review:** this issue is done and awaits a code review. Remove the label once the code review has been conducted and the PR is merged or closed.

Feel free to create more labels if the existing ones don't fit your case.
