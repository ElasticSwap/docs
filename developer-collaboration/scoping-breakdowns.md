# Scoping & Breakdowns

## Why Are We Doing This?

- Breaking down complex topics into epics and user stories helps us tackle work in the proper order and avoid losing an overview or goal. Additionally, breaking down bigger tasks early on makes writing and reviewing code more manageable.
- Ensuring transparency by enabling all team members to see what everyone is working on, which issues are blocking/blocked, and how much workload we currently have.
- Creating user stories helps us build features from the user's perspective and ensures that we tailor the experience toward them. It's an easy way to cover all bases and think about edge cases before starting the implementation.

## Getting Started

Before working on a task, we first need to document it in GitHub. This also means breaking down complex topics into smaller subtasks with dependencies between each other.

As a rule of thumb, if you need more than one day to work on an issue or cover many different aspects (e.g., creating a design, writing front-end code, and updating the SDK), it should be broken up into smaller tasks.

The main advantage here is smaller PRs, making for easier code reviews. Nobody wants to review 5,000 line changes in a single PR, as this can become cumbersome quickly and lead to overseen bugs eventually landing in production.

So before you start writing code, think about the task as a whole and how you could potentially break it up into smaller subtasks. Then, please create a new issue in the appropriate repository for each task and link them to make dependencies clear. If a task is small enough or it doesn't make sense to break it up, then create just one issue.

The next section will cover best practices for creating new issues and epics.
