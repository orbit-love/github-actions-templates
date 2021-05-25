# Reddit Integration Template

This integration runs every 24 hours and checks for new posts in a specified subreddit.

This data will be added to your Orbit workspace as new activities.

> If you are a developer and want to incorporate this integration into your existing applications then please check out the [standalone JavaScript library](https://github.com/orbit-love/community-js-reddit-orbit).

## Instructions

1. Go to your repository created during your [first-time setup](../FIRST_TIME_SETUP.md) and click on the Actions tab.
2. Click "set up a workflow yourself" and call it youtube.yml - delete the content so it is blank.
3. Copy the contents of [reddit.yml](reddit.yml) into your new workflow.
4. Edit the items underneath line 11 to add your subreddits to watch.
5. This automation requires credentials from YouTube to be added to your GitHub repository secrets.
    1. Head to your [Reddit App Preferences](https://www.reddit.com/prefs/apps/).
    2. Create a new app with the following settings:
        1. Name: `orbit-community-integration`
        2. Type: `script`
        3. Description: `orbit.love community integration`
        4. About URL: `https://github.com/orbit-love/community-js-reddit-orbit`
        5. Redirect URI: `https://orbit.love`
    3. Take note of your `Client ID` which is just below your app name, and your `Client Secret`.
    4. Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add `REDDIT_CLIENT_ID`, `REDDIT_CLIENT_SECRET`, `REDDIT_USERNAME`, and `REDDIT_PASSWORD` values.

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.
