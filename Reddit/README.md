# Reddit Integration Template

This integration runs every hour and checks for new posts and comments in a specified subreddit. This data will be added to your Orbit workspace as new activities.

![](https://github.com/orbit-love/community-js-reddit-orbit/blob/main/docs/activity-post.png)
![](https://github.com/orbit-love/community-js-reddit-orbit/blob/main/docs/activity-comment.png)

> If you are a developer and want to incorporate this integration into your existing applications then please check out the [standalone JavaScript library](https://github.com/orbit-love/community-js-reddit-orbit).

## Instructions

1. Go to your repository created during your [first-time setup](../FIRST_TIME_SETUP.md) and click on the Actions tab.
2. Click "set up a workflow yourself" and call it reddit.yml - delete the content so it is blank.
3. Copy the contents of [reddit.yml](reddit.yml) into your new workflow.
4. Edit the items underneath line 11 to add your subreddits to watch.
5. This automation requires credentials from Reddit to be added to your GitHub repository secrets. The Reddit account cannot have 2FA enabled. If yours has 2FA enabled, please create a new Reddit username without 2FA to use for the import.
   1. Head to your [Reddit App Preferences](https://www.reddit.com/prefs/apps/).
   2. Create a new app with the following settings:
      1. Name: `orbit-community-integration`
      2. Type: `script`
      3. Description: `orbit.love community integration`
      4. About URL: `https://github.com/orbit-love/community-js-reddit-orbit`
      5. Redirect URI: `https://orbit.love`
   3. Take note of your `Client ID` which is just below your app name, and your `Client Secret`.
   4. Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add `REDDIT_CLIENT_ID`, `REDDIT_CLIENT_SECRET`, `REDDIT_USERNAME`, and `REDDIT_PASSWORD` values.

### Filtering Posts & Comments

You can pass in a `--filter=term` flag to filter the results by a single term. To do this, find the line in the template which starts `npx @orbit-love/reddit` and add a space and `--filter="your term"` to the end.

- For posts this will match if the post title, url or body text contain the term.
- For comments this will match if it was left on a post with a title containing the term, or the comment itself contains the term.
- For both the filter term is not case sensitive.

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.

### Performing a Historical Import

You may want to perform a one-time historical import to fetch all your previous LinkedIn interactions and bring them into your Orbit workspace. Set the hours tag to 720 for 30 days of import to do so.

Change the `hours` value on line 20 in your `orbit-integrations/actions/workflows/reddit.yml`. Then head to your actions and re-run the workflow manually. Once run successfully, disable the current workflow, change the `hours` value back to 1, and find the workflow in the actions tab and enable it.
