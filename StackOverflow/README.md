# Stack Overflow Integration Template

This integration runs every hour and checks for new questions on Stack Overflow with the provided tag.

This data will be added to your Orbit workspace as new activities.

> If you are a developer and want to incorporate this integration into your existing applications then please check out the [standalone JavaScript library](https://github.com/orbit-love/community-js-stackoverflow-orbit).

## Instructions

1. Go to your repository created during your [first-time setup](../FIRST_TIME_SETUP.md) and click on the Actions tab.
2. Click "set up a workflow yourself" and call it stackoverflow.yml - delete the content so it is blank.
3. Copy the contents of [stackoverflow.yml](stackoverflow.yml) into your new workflow.
4. Find the line that reads `run: npx @orbit-love/stackoverflow --questions --hours=1 --tag=PutYourTagHere` and replace `PutYourTagHere` with the tag you wish to watch.
5. This automation requires credentials from Stack Overflow to be added to your GitHub repository secrets.
    1. Head to [Stack Apps](https://stackapps.com) and login in to your account.
    2. [Register a new Stack Apps application](https://stackapps.com/apps/oauth/register). The oauth domain can be anything, as can the application website.
    3. In your application settings, take note of your `Key` value.
    4. Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add a `STACK_APPS_KEY` secret using the `Key` value from the previous step.

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.

Note: if you want to run this for several tags, create multiple workflows and provide one tag in each.
