# DEV Integration Template

> Automate integrating DEV interactions into your Orbit workspace with this GitHub Actions template

![Screenshot of activity](new-comment-screenshot.png)

<hr />

There are three checks included in the DEV automation template, they all occur once a day.

Two of the checks are for DEV user accounts (i.e. a personal profile):

1. Check for new blog post comments
2. Check for new followers

One check is for a DEV organization account (i.e. a company profile):

1. Check for new blog post comments

If there are new followers or new blog post comments in any of the checks they will be added to your Orbit workspace as new members or new activities, respectively.

**To use this workflow for a DEV user account:**

* Copy the [dev.yml](https://github.com/orbit-love/github-actions-templates/blob/main/DEV/dev.yml) file into your own GitHub repository inside your `.github/workflows` directory
* Remove lines 38-45 in the file, which is for a DEV organization workflow

* The automation requires your DEV and Orbit credentials be added to your GitHub repository secrets.
    * Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add the following two additional secrets:
        * `DEV_API_KEY`: Your DEV API key
        * `DEV_USERNAME`: Your DEV user account name

* This workflow will automatically filter out any DEV comments that are older than the most recent DEV comment in your Orbit workspace currently.
    * To perform a historical import, that will send to Orbit **all** of your DEV comments add the `--historical-import` flag to the workflow file on line 24: `dev_orbit --check-comments --historical-import`
    * **You should only need to run a historical import once, and it is recommended to remove the `--historical-import` flag after.**

**To use this workflow for a DEV organization account:**

* Copy the [dev.yml](https://github.com/orbit-love/github-actions-templates/blob/main/DEV/dev.yml) file into your own GitHub repository inside your `.github/workflows` directory
* Remove lines 22-37 in the file, which is for a DEV user workflow

* The automation requires your DEV and Orbit credentials be added to your GitHub repository secrets.
    * Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add the following two additional secrets:
        * `DEV_API_KEY`: Your DEV API key
        * `DEV_ORGANIZATION`: Your DEV organization name (i.e. `orbit` for the Orbit organization on DEV)

* This workflow will automatically filter out any DEV comments that are older than the most recent DEV comment in your Orbit workspace currently.
    * To perform a historical import, that will send to Orbit **all** of your DEV comments add the `--historical-import` flag to the workflow file on line 40: `dev_orbit --check-organization-comments --historical-import`
    * **You should only need to run a historical import once, and it is recommended to remove the `--historical-import` flag after.**

**To use this workflow for *both* a DEV organization and a DEV user:**

* Copy the [dev.yml](https://github.com/orbit-love/github-actions-templates/blob/main/DEV/dev.yml) file into your own GitHub repository inside your `.github/workflows` directory

* The automation requires your DEV and Orbit credentials be added to your GitHub repository secrets.
    * Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add the following three additional secrets:
        * `DEV_API_KEY`: Your DEV API key
        * `DEV_USERNAME`: Your DEV user account name
        * `DEV_ORGANIZATION`: Your DEV organization name (i.e. `orbit` for the Orbit organization on DEV)

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.
