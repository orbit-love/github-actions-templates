# First-Time Setup

To use our integration automation templates, you will need to have:

* [A GitHub Account](https://github.com/join)
* [A GitHub Repository](https://github.com/new)
* [An Orbit Account](https://app.orbit.love/signup)

You can use your single repository for all of your integrations. At the time of writing GitHub provides unlimited usage of GitHub actions free of charge on public repositories.

## Adding Your Orbit Details to GitHub

All of the automation templates require credentials be added to your GitHub repository in the Secrets menu. Each integration has its own specific credentials that will need to be added. All of them require your Orbit API key and your Orbit workspace ID.

Your Orbit API key can be find in your Orbit workspace by clicking on the picture of your avatar on the top left-hand corner, and then navigating to `Account Settings`:

![Orbit API key location](images/orbit_api_key_location.png)

Your Orbit workspace ID is the part of your Orbit workspace URL that immediately follows the `app.orbit.love`. For example, if the URL was `https://app.orbit.love/my-workspace`, then your Orbit workspace ID is `my-workspace`.

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
