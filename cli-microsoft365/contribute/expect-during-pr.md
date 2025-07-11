-e <!-- DISCLAIMER: All secrets, passwords, and sensitive values in this document are examples only and not real credentials. -->
# What to expect during a Pull Request review

At CLI for Microsoft 365, we appreciate your contributions through pull requests (PRs) for the issues you're helping us with. The review process is a collaborative effort between you and the maintainers who review your code. Depending on availability, your PR may be reviewed by one or more reviewers.

We prioritize processing PRs in the order they are received (first in, first out). PRs with bug fixes are given priority over new features and enhancements because they address active issues that impact our users. When a PR requires adjustments after review, it is moved to the end of the processing queue to prevent blocking the review process.

This article aims to provide an understanding of how we review pull requests, what you can expect during the review process, and how a pull request is merged or closed.

## What happens immediately after submitting a PR?

Once you submit a PR, one of our maintainers will examine it and check if the PR build has passed. The automated checks include:

- Successful code build
- Passing automated tests with 100% coverage
- Absence of issues caught by our linter (ensuring adherence to naming conventions and code consistency)

PRs are reviewed in the order of their submission, and once reviewed, they are moved to the end of the queue. If issues are identified during the review, the maintainers promptly notify the author to rectify them before proceeding with the review.

## Review process and feedback

When your PR is under review, the assigned maintainer will indicate their involvement by assigning themselves to the PR. They will follow a checklist for the review process, which can be found [here](./pr-checklist.mdx).

Maintainers may also provide suggestions for best practices to ensure consistent coding styles. If there are code-related comments, you will see "changes requested" next to your username in the PR. In case the maintainer needs your input on an issue before continuing the review, the PR will be labelled as "waiting on response." The reviewer will also mark the pull request as **draft** to indicate that it is `work in progress` and that changes are expected to be made.

## Updating the PR after feedback

After receiving feedback from reviewers on your pull request, you might need to make some changes to address their comments or suggestions. Once you've made the necessary adjustments, it's essential to update the PR so that the reviewers can reevaluate the changes. One of the best approaches for updating a PR is by using [rebase](https://docs.github.com/get-started/using-git/about-git-rebase).

:::note

To make the life of the reviewers easier, please do **NOT** merge the `main` branch into your PR branch. Instead, use `rebase` to update your PR branch with the latest changes from the `main` branch. This keeps the commit history clean and makes it easier for reviewers to merge the changes you've made.

<details>
  <summary>Click here for a sample on how to rebase your branch</summary>

  When you are ready to sync your PR branch with the latest changes, ensure that your `main` branch is synced on your GitHub fork.

  ![Sync fork](../images/contribute/Sync-fork.png)

  Next execute the following commands in your terminal:

  ```powershell
  # Checkout your main branch
  git checkout main

  # Pull latest changes
  git pull

  # Checkout your PR branch
  git checkout <your-pr-branch>

  # Rebase your PR branch with the latest changes from main
  git rebase main

  # When encountering conflicts, resolve them and press 'continue' in your code editor until the rebase is finished

  # Push the rebased branch to your fork
  git push --force
  ```

</details>

:::

After making the necessary changes based on the review feedback, you can mark the PR as **ready for review** to signal that it is ready for another round of review by the maintainers. This will put the PR back into the backlog for the reviewers.

## Finalizing the PR review

During the subsequent review, the maintainer will perform another round of evaluation. If further changes are needed, the review cycle continues. Once everything is satisfactory, the reviewer will approve the PR and label it as `pr-merged`. This indicates that your PR has been fully approved and merged into the main branch of the source code. You will receive a comment from the reviewer notifying you of the merge. The reviewer will then close the PR, and subsequently, the associated issue will also be closed.

## Response time for requested changes

Reviewers will wait for four weeks after requesting changes before closing a PR. They will follow up with you before closing it. You can open a new PR at any time after syncing your fork.

By following these steps and understanding the review process, we can collaborate effectively to incorporate your awesome contributions into the CLI for Microsoft 365.
