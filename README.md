# Pullfrog Preview Template

This is a template repository used for creating preview testing repos for Pullfrog action development.

## How it works

When a PR is opened on `pullfrog/app` that modifies the `action/` directory:

1. A new repo `pullfrog/preview-<pr_number>-<branch>` is created from this template
2. A `.branch` file is pushed containing the PR branch name
3. Secrets are copied to the new repo
4. Webhooks from the preview repo are forwarded to the Vercel preview deployment

## Testing

To test the Pullfrog action from a PR branch:

1. Create an issue or PR in the preview repo
2. Mention `@pullfrog` with a task
3. The workflow will checkout and build the action from the PR branch

## Files

- `.github/workflows/pullfrog.yml` - The Pullfrog workflow that reads `.branch` and builds from that branch
- `.branch` - Created by CI, contains the PR branch name to checkout
