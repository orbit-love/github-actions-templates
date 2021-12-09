# YouTube Integration Template

This integration runs every 24 hours and checks for new comments on every video on a specified channel. This data will be added to your Orbit workspace as new activities.

![](https://raw.githubusercontent.com/orbit-love/community-js-youtube-orbit/main/docs/activity.png)

> If you are a developer and want to incorporate this integration into your existing applications then please check out the [standalone JavaScript library](https://github.com/orbit-love/community-js-youtube-orbit).

## Instructions

1. Go to your repository created during your [first-time setup](../FIRST_TIME_SETUP.md) and click on the Actions tab.
2. Click "set up a workflow yourself" and call it youtube.yml - delete the content so it is blank.
3. Copy the contents of [youtube.yml](youtube.yml) into your new workflow.
4. This automation requires credentials from YouTube to be added to your GitHub repository secrets.
    1. Create a project in the [Google Developers Console](https://console.developers.google.com/)
    2. After creating your project, make sure the YouTube Data API is one of the services that your application is registered to use.
    3. Go to the Credentials area of your application and create an API Key. Take note of the API Key as it will only be shown once.
    4. Get your Channel's ID by [following these steps](https://support.google.com/youtube/answer/3250431).
    5. Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add `YOUTUBE_API_KEY` and `YOUTUBE_CHANNEL_ID` values.

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.

## Notes about quota

Please take a moment to read the [quota usage](https://developers.google.com/youtube/v3/getting-started#quota) section of the YouTube Data API documentation. Per request this application:

- makes one list channel request
- makes one list videos request for every 50 videos on your channel
- makes one list commentThread request for every video with at least one comment

This should be fine for a majority of channels, but if you are concerned you will exceed the quota follow the provided guide on how to request a quota increase.

## Performing a Historical Import
You may want to perform a one-time historical import to fetch all your previous YouTube interactions and bring them into your Orbit workspace. Set the hours tag to 720 for 30 days of import to do so. [You may want to import less history based on your quota.](#notes-about-quota)

Change the hours value on line 16 in your orbit-integrations/actions/workflows/youtube.yml. Then head to your actions and re-run the workflow manually. Once run successfully, disable the current workflow, change the hours value back to 24, and find the workflow in the actions tab and enable it.
