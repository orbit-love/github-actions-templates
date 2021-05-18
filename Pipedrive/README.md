# Pipedrive Integration Template
> Automate integrating Pipedrive interactions into your Orbit workspace with this GitHub Actions template

<hr />

There is one check included in the Pipedrive automation template, it occurs once a day:

1. Check for new notes on deals

If there are new notes they will be added to your Orbit workspace as new activities.

To use this workflow:

* Copy the [pipedrive.yml](https://github.com/orbit-love/github-actions-templates/blob/main/Pipedrive/pipedrive.yml) file into your own GitHub repository inside your `.github/workflows` directory

* The automation requires your Pipedrive and Orbit credentials be added to your GitHub repository secrets.
    * Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add the following two additional secrets:
        * `PIPEDRIVE_URL`: Your Pipedrive organization website, i.e. `https://example-12345.pipedrive.com`.
        * `PIPEDRIVE_API_KEY`: Your Pipedrive API key, found in `Personal Settings -> API` in your Pipedrive workspace.

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.
