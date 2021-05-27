# Notion Integration Template
> Automate integrating Notion notion into your Orbit workspace with this GitHub Actions template

![Screenshot of activity in Orbit workspace](https://raw.githubusercontent.com/orbit-love/community-ruby-notion-orbit/main/docs/new-note-screenshot.png)

<hr />

There is one check included in the Notion automation template, it occurs once a day:

1. Check for new notes in the Notion database

If there are new notes they will be added to your Orbit workspace.

To use this workflow:

* Copy the [notion.yml](https://github.com/orbit-love/github-actions-templates/blob/main/Notion/notion.yml) file into your own GitHub repository inside your `.github/workflows` directory

* The automation requires your Notion API key, Notion workspace slug and Notion database ID be added to your GitHub repository secrets.
    * Follow the steps in the [GitHub Actions Templates First Time Setup Guide](https://github.com/orbit-love/github-actions-templates/blob/main/FIRST_TIME_SETUP.md) and add the following additional secret:
        * `NOTION_API_KEY`: Follow the [Notion Integration Setup Guide](https://github.com/orbit-love/community-ruby-notion-orbit/blob/main/docs/setup.md) for instructions on obtaining your API key
        * `NOTION_WORKSPACE_SLUG`: If your website address is `https://notion.so/my-workspace/` then your slug is `my-workspace`
        * `NOTION_DATABASE_ID`: Your database ID the part of your Notion database URL that follows after your workspace slug and before the question mark (`?`). The ID is 32 characters long, containing numbers and letters.<br/>![Database ID location](https://raw.githubusercontent.com/orbit-love/community-ruby-notion-orbit/main/docs/database-id-location.png)
            * **You must add your Notion application integration that you created in the [Notion Integration Setup Guide](https://github.com/orbit-love/community-ruby-notion-orbit/blob/main/docs/setup.md) to the database that you wish to fetch notes from.**
                * From the top navigation bar in your Notion database view press the "Share" button
                * Find your Notion application integration by the name you gave it in the Notion request form
                * Select the integration and click "Invite"
                    ![](https://files.readme.io/0a267dd-share-database-with-integration.gif)

Once the workflow and credentials have been added to your GitHub repository, the workflow will be activated. You do not need to do anything else to activate it.
