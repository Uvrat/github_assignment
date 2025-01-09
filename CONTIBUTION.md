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
- If your PR refers to or fixes an issue, be sure to add `refs #XXX` or `fixes #XXX` to the PR description. Replacing `XXX` with the respective issue number. See more about [Linking a pull request to an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue).
- Be sure to fill the PR Template accordingly.
- Review [App Contribution Guidelines](./packages/app-store/CONTRIBUTING.md) when building integrations

Pull Request (PR) Format

When submitting a pull request, follow the format below:

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

Example PR Description

## Guidelines for committing yarn lockfile

Do not commit your `yarn.lock` unless you've made changes to the `package.json`. If you've already committed `yarn.lock` unintentionally, follow these steps to undo:

If your last commit has the `yarn.lock` file alongside other files and you only wish to uncommit the `yarn.lock`:

```bash
git checkout HEAD~1 yarn.lock
git commit -m "Revert yarn.lock changes"
```

_NB_: You may have to bypass the pre-commit hook with by appending `--no-verify` to the git commit
If you've pushed the commit with the `yarn.lock`:

1.  Correct the commit locally using the above method.
2.  Carefully force push:

```bash
git push origin <your-branch-name> --force
```

If `yarn.lock` was committed a while ago and there have been several commits since, you can use the following steps to revert just the `yarn.lock` changes without impacting the subsequent changes:

1. **Checkout a Previous Version**:

   - Find the commit hash before the `yarn.lock` was unintentionally committed. You can do this by viewing the Git log:

     ```bash
     git log yarn.lock
     ```

   - Once you have identified the commit hash, use it to checkout the previous version of `yarn.lock`:

     ```bash
     git checkout <commit_hash> yarn.lock
     ```

2. **Commit the Reverted Version**:

   - After checking out the previous version of the `yarn.lock`, commit this change:

     ```bash
     git commit -m "Revert yarn.lock to its state before unintended changes"
     ```

3. **Proceed with Caution**:

   - If you need to push this change, first pull the latest changes from your remote branch to ensure you're not overwriting other recent changes:

     ```bash
     git pull origin <your-branch-name>
     ```

   - Then push the updated branch:

     ```bash
     git push origin <your-branch-name>
     ```

Lastly, make sure to keep the branches updated (e.g. click the `Update branch` button on GitHub PR).
