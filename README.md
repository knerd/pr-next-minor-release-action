# 🔖 Create Next Minor Release PR

This GitHub Action automatically dispatches a next minor release. The action is designed to streamline the process of creating a pull request for the next minor release from your development branch.

## Inputs

This action accepts the following inputs:

- `MAIN` (optional, default: `'main'`): The name of the main branch, used as the PR destination.
- `DEVELOP` (optional, default: `'develop'`): The name of the develop branch, used as the reference to cut the release branch from.
- `BOT_NAME` (optional, default: `'🤖 knerd-bot'`): The name of the bot.
- `BOT_EMAIL` (optional, default: `'contact@midnightnerd.com'`): The email of the bot.
- `PR_TEMPLATE` (optional, default: `'.github/PULL_REQUEST_TEMPLATE.md'`): The template to use for PR creation.

## Example usage

```yml
- name: 👆🔖 Dispatch Next Minor Release w/ PR
  uses: knerd/pr-next-minor-release-action@v1
  with:
    MAIN: 'main'
    DEVELOP: 'develop'
    BOT_NAME: '🤖 knerd-bot'
    BOT_EMAIL: 'contact@midnightnerd.com'
    PR_TEMPLATE: '.github/PULL_REQUEST_TEMPLATE.md'
