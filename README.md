# 🔖 Create Next ${NPM_VERSION} Release PR Action

This GitHub Action automatically dispatches a next `npm version $NPM_VERSION` release. It is designed to streamline the process of creating a pull request for the next minor release from your development branch.

## Inputs

This action accepts the following inputs:

- `GITHUB_TOKEN` (required): The GitHub Token for the repository. This is used to push the new branch and create the PR.
- `MAIN` (optional, default: `'main'`): The name of the main branch, used as the PR destination.
- `DEVELOP` (optional, default: `'develop'`): The name of the develop branch, used as the reference to cut the release branch from.
- `BOT_NAME` (optional, default: `'🤖 knerd-bot'`): The name of the bot.
- `BOT_EMAIL` (optional, default: `'contact@midnightnerd.com'`): The email of the bot.
- `PR_TEMPLATE` (optional, default: `'.github/PULL_REQUEST_TEMPLATE.md'`): The template to use for PR creation.
- `PR_DRAFT` (optional): Flag to turn on draft PRs.
- `PR_LABEL` (optional): Label for the PR.
- `PR_ICON` (optional, default: `🔖`): Emoji to use as prefix for PR.
- `NPM_VERSION` (optional, default: `minor`): Version to bump.

## Usage

Include the action in your workflow file as follows:

```yml
# For your next minor release workflow
- name: 👆🔖 Dispatch Next Minor Release w/ PR
  uses: knerd/pr-next-minor-release-action@v1
  with:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
    NPM_VERSION: 'minor'
    PR_LABEL: 'release'
    PR_ICON: '🔖'
    # MAIN: 'main'
    # DEVELOP: 'develop'
    # BOT_NAME: '🤖 knerd-bot'
    # BOT_EMAIL: 'contact@midnightnerd.com'
    # PR_TEMPLATE: '.github/PULL_REQUEST_TEMPLATE.md'
    # PR_DRAFT: true

# For your hotfix workflow
- name: ♨️ Dispatch hotfix branch w/ PR
  uses: knerd/pr-npm-version-action@v1
  with:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
    NPM_VERSION: patch 
    PR_LABEL: ♨️ hotfix 
    PR_ICON: ♨️ 
    # MAIN: 'main'
    # DEVELOP: 'develop'
    # BOT_NAME: '🤖 knerd-bot'
    # BOT_EMAIL: 'contact@midnightnerd.com'
    # PR_TEMPLATE: '.github/PULL_REQUEST_TEMPLATE.md'
    # PR_DRAFT: true