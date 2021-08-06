# Meetup Integration Template
> Automate integrating Meetup interactions into your Orbit workspace with this GitHub Actions template

<hr />

There is one checks included in the Meetup automation template, it occurs once a day:

1. Check for new event RSVPS for a Meetup group

If there are new RSVPs they will be added to your Orbit workspace.

To use this workflow:

* Copy the [meetup.yml](https://github.com/orbit-love/github-actions-templates/blob/main/Meetup/meetup.yml) file into your own GitHub repository inside your `.github/workflows` directory

* The automation requires your Meetup group URL identifier be added to your GitHub repository secrets.
    * Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add the following additional secret:
        * `MEETUP_URLNAME`: Your Meetup group URL ID, i.e. if your Meetup group URL is `https://www.meetup.com/meetup-group-test-123` then your group ID is `meetup-group-test-123`

* This workflow will automatically filter out any Meetup RSVPs that are older than the most recent RSVP for an event in your Orbit workspace currently.
    * To perform a historical import, that will send to Orbit **all** of your Meetup RSVPs for events add the `--historical-import` flag to the workflow file on line 24: `meetup_orbit --check-rsvps --historical-import`
    * **You should only need to run a historical import once, and it is recommended to remove the `--historical-import` flag after.**

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.
