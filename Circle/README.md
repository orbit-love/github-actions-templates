# Circle Integration Template
> Automate integrating Circle interactions into your Orbit workspace with this GitHub Actions template
![Screenshot of Activity](https://raw.githubusercontent.com/orbit-love/community-ruby-circle-orbit/main/readme-images/screenshot_of_activity.png)
<hr />

There are two checks included in the Circle automation template, they occur once a day:

1. Check for new posts in your Circle Spaces
2. Check for new comments on posts in your Circle Spaces

If there are new posts or comments they will be added to your Orbit workspace.

To use this workflow:

* Copy the [circle.yml](https://github.com/orbit-love/github-actions-templates/blob/main/Circle/circle.yml) file into your own GitHub repository inside your `.github/workflows` directory

* The automation requires your Circle API key and your Circle community URL be added to your GitHub repository secrets.
    * Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add the following additional secret:
        * `CIRCLE_API_KEY`: Create a new API key in the API section in your User Settings
        * `CIRCLE_URL`: This is your Circle custom URL, for example: `https://orbit.circle.so`

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.
