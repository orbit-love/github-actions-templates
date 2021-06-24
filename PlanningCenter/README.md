# Planning Center Integration Template
> Automate integrating Planning Center interactions into your Orbit workspace with this GitHub Actions template

![Screenshot of activity](new-checkin-screenshot.png)

<hr />

There is one check included in the Planning Center automation template, it occurs once a day:

1. Check for new event check-ins for a Planning Center event

If there are new check-ins they will be added to your Orbit workspace.

To use this workflow:

* Copy the [planning_center.yml](https://github.com/orbit-love/github-actions-templates/blob/main/PlanningCenter/planning_center.yml) file into your own GitHub repository inside your `.github/workflows` directory

* The automation requires your Planning Center app ID and Planning Center API secret group URL be added to your GitHub repository secrets.
    * Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add the following additional secrets:
        * `PLANNING_CENTER_APP_ID`: Create a new "Personal Access Token" in the [Planning Center Developer Dashboard](https://api.planningcenteronline.com/oauth/applications), your Application ID will be shown after creating it.
        * `PLANNING_CENTER_API_SECRET`: Planning Center API secret | Create a new "Personal Access Token" in the [Planning Center Developer Dashboard](https://api.planningcenteronline.com/oauth/applications), your API secret will be shown after creating it.

* This workflow will automatically filter out any Planning Center activities that are older than the most recent Planning Center activity in your Orbit workspace currently.
    * To perform a historical import, that will send to Obit **all** of your Planning Center activities add the `--historical-import` flag to the workflow file on line 24: `planningcenter_orbit --check-event-checkins --historical-import`
    * **You should only need to run a historical import once, and it is recommended to remove the `--historical-import` flag after.**

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.
