# Contribution Guidelines

Thank you for considering contributing to this project! By contributing, you help make this project better, and we value your input. This guide outlines the basic rules and format for contributions, including pull requests (PRs).

## Developing

The development branch is `main`. This is the branch that all pull
requests should be made against.

To develop locally:

1. [Fork](https://github.com/Zzzzssssss/github_assignment/fork/) Start by forking the repository to your GitHub account.
   Clone the Repository:
   ```sh 
    git clone https://github.com/your-username/github_assignment.git
   ```
   Set Upstream Remote:
   ```sh 
    git remote add upstream https://github.com/Zzzzssssss/github_assignment.git
    ```

2. Create a new branch:
   ```sh
   git checkout -b MY_BRANCH_NAME
   ```
   
3. Install the dependencies:

   ```sh
   npm i
   ```
4. Set up your `.env` file:
    - Duplicate `.env.example` to `.env`.
5. Start Services:
   Run the following command to start the DB and other dev services:
      ```sh
   docker-compose up -d
   ```

6. Start developing and watch for code changes:

   ```sh
   npm run dev
   ```

## Building

You can build the project with:

```bash
npm run build
```

Please be sure that you can make a full production build before pushing code.


## Running tests


### Linting

To check the formatting of your code:

```sh
npm run lint
```

If you get errors, be sure to fix them before committing.

## Making a Pull Request

- Be sure to [check the "Allow edits from maintainers" option](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/allowing-changes-to-a-pull-request-branch-created-from-a-fork) while creating your PR.
- Be sure to fill the PR Template accordingly.
Pull Request (PR) Format

When submitting a pull request, follow the format below:

```sh
PR Title

Use a concise and descriptive title that summarizes your changes. Examples:

"Fix bug in authentication module"

"Add unit tests for utility functions"

"Improve performance of data processing pipeline"

PR Description

Provide a clear and detailed description of your changes. Include the following sections:

Summary: Briefly summarize what your PR does.

Related Issues: Link any related issues using keywords like "Closes #123".

Changes Made: List the major changes made in your PR.

Testing Details: Describe how you tested your changes.
```
