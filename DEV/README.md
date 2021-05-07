# DEV Integration Template

> Automate integrating DEV interactions into your Orbit workspace with this GitHub Actions template

<hr />

There are two checks included in the DEV automation template, they both occur once a day:

1. Check for new blog post comments
2. Check for new followers

If there are new followers or new blog post comments they will be added to your Orbit workspace as new members or new activities, respectively.

To use this workflow:

* Copy the [new_interaction.yml](https://github.com/orbit-love/github-actions-templates/blob/main/DEV/new_interactions.yml) file into your own GitHub repository inside your `.github/workflows` directory

* The automation requires your DEV and Orbit credentials be added to your GitHub repository secrets.
    * Follow the steps in the [Adding Your Credentials to GitHub](https://github.com/orbit-love/github-actions-templates/blob/main/README.md#adding-your-credentials-to-github) section in the main README with the following two additional secrets:
        * `DEV_API_KEY`: Your DEV API key
        * `DEV_USERNAME`: Your DEV username

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.
