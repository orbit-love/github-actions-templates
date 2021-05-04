# GitHub Actions Templates
> Automate community integrations for your Orbit workspace with these GitHub Actions template starter files

<hr />

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.0-4baaaa.svg)](code_of_conduct.md)
# Table of Contents
* [Overview](#overview)
    * [Adding Your Credentials to GitHub](#adding-your-credentials-to-github)
* [Integration Instructions](#integration-instructions)
    * [DEV](#dev)
* [Contributing](#contributing)
* [Code of Conduct](#code-of-conduct)
* [License](#license)

# <a name="overview"></a>Overview

Each directory in this repository contains an automation workflow template for a specific community-built integration for Orbit workspaces.

## <a name="adding-your-credentials-to-github"></a>Adding Your Credentials to GitHub

All of the automation templates require credentials be added to your GitHub repository in the Secrets menu. Each integration has its own specific credentials that will need to be added. All of them require your Orbit API key and your Orbit workspace ID.

Your Orbit API key can be find in your Orbit workspace by clicking on the picture of your avatar on the top left-hand corner, and then navigating to `Account Settings`:

![Orbit API key location](images/orbit_api_key_location.png)

Your Orbit workspace ID is the part of your Orbit workspace URL that immediately followers the `app.orbit.love`. For example, if the URL was `https://app.orbit.love/my-workspace`, then your Orbit workspace ID is `my-workspace`.

Follow these steps to add your `ORBIT_API_KEY` and `ORBIT_WORKSPACE_ID` to your GitHub repository secrets:

* Navigate to the `Settings` section in your GitHub repository:
![GitHub Settings Tab](images/github_settings_tab.png)
* Then, click on the `Secrets` link from the side navigation bar:

    ![GitHub Secrets Link](images/github_secrets_navbar.png)
* Once you are on the Secrets page, click on the `New repository secret` button:
![New secret button](images/new_secret_button.png)
* Then, fill out the prompt with your credential information:
![New secret prompt](images/new_secret_prompt.png)

> **Repeat the new secret step for each unique secret:**
* `ORBIT_API_KEY`: Your Orbit API key
* `ORBIT_WORKSPACE_ID`: Your Orbit workspace ID
* ... other secrets for specific integrations
# <a name="integration-instructions"></a>Integration Instructions

The following integration workflows are available to use, and more will be added:

* [DEV Community Blog](#dev)

To use a workflow, please read the instructions in the section pertaining to that integration.
## <a name="dev"></a>DEV

There are two checks included in the DEV automation template:

1. Check for new blog post comments
2. Check for new followers

Each check is scheduled to occur once a day. If there are new followers or new blog post comments they will be added to your Orbit workspace as new members or new activities, respectively.

To use this workflow:

* Copy the [new_interaction.yml](https://github.com/orbit-love/github-actions-templates/blob/main/DEV/new_interactions.yml) file into your own GitHub repository inside your `.github/workflows` directory

* The automation requires your DEV and Orbit credentials be added to your GitHub repository secrets.
    * Follow the steps in the [Adding Your Credentials to GitHub](#adding-your-credentials-to-github) section with the following two new secrets:
        * `DEV_API_KEY`: Your DEV API key
        * `DEV_USERNAME`: Your DEV username


# <a name="contributing"></a>Contributing

We :heart: contributions! Please read the [Contribution Guidelines](CONTRIBUTING.md) on how to get involved.
# <a name="code-of-conduct"></a>Code of Conduct

This project has a [Contributor Code of Conduct](CODE_OF_CONDUCT.md). We ask everyone to please adhere by its guidelines.

# <a name="license"></a>License

This project is under the [MIT License](LICENSE).