# CogArch_Markdown


## Introduction
This is the markdown repository template for the "Export to GitHub Pages" utility in [Cognitive Architect](https://w3.ibm.com/tools/cogarch/).  

The export function creates markdown files containing the architecture information and then uses [MkDocs](https://www.mkdocs.org), [MkDocs Awesome Pages plugin](https://github.com/lukasgeiter/mkdocs-awesome-pages-plugin) and [Material for MkDocs theme](https://squidfunk.github.io/mkdocs-material/getting-started/) to generate the corresponding GitHub Pages of the architecture.  

It consists of the following folders:
- docs
- template
  - official_template : contains the architectural artifacts' default templates
  - user_template : user-defined templates that overrides the default
- theme : contains the theme used for the generated pages
  - assets : ???
  - partials : ???
  - extra.css (file) : ???
  - extra.js (file) : ???

and files:
- Makefile : for redeploying changes made to the markdown files 
  - only markdown? what about changes to the ejs files?
- README.md : this page
- mkdocs.yml : configuration file for ???
- requirements.txt : ???

When the export is successfully executed, the markdown files containing the architecture information will be stored in the `docs` folder.



## Setup

Before executing the export utility, the following setup is required:


1. Make a copy of the markdown repository template to your own GitHub repository by doing one of the following:
   - *Fork* the repository or
   - *Download* the repository directly
2. Generate the GitHub token with ***repo***  access. This is needed so that the export utility can generate the appropriate files into your GitHub repo.  
For help on creating the token, go to [GitHub Repo URL & Token](#github-repo-token--url).


💡 Tip: At a minimum, each architecture should have its own git repository! If you want to show different content based on your target audience or purpose, export them to different git repositories.



## Usage in Cognitive Architect : Export Utility

1. Go to the Export / Import menu in cogArch
2. Provide your github repository link and token
3. Click the Export button
4. The Export utility will execute in the background and you will be notified and provided with the link to the published pages when the export is done.


⚠️ Warning: Do not close the browser window after the Export request has been submitted! The URL of your GitHub Pages will be returned when the export is completed.


If you did not see or get the URL, your GitHub Pages can be accessed using the following format:  
`https://pages.github.ibm.com/{github_account}/{repo_name}/Information/`or  
`https://pages.github.com/{github_account}/{repo_name}/Information/`



## GitHub Repo Token & URL

To generate an access token for your repository:
 - Navigate to [repository-url]/settings/tokens/new (e.g. https://github.ibm.com/settings/tokens/new)
 - Add a description, for e.g. cogArch-access and select *repo* scope
 - Click the "Generate Token" button
 - Click on the clipboard icon (📋) to copy the token and save it somewhere. You will need this in the "Export dialog" in Cognitive Architect. Note that you cannot retrieve the token from Git after you leave the Token generation page.


Which repository URL to use will depend on whether you are accessing an Enterprise or Public Git repository.
- For accessing an Enterprise Git repository, a SSH URL with a mandatory access token is the only supported configuration. In general, the access token is required for the export (write to repository). 
- For a public Git repository, you can supply an HTTPS repository URL. This allows for such sites to host architectures for download without the need of an access token.


Sample URLs
- A sample SSH URL for an Enterprise Git repository is `git@github.ibm.com:jang/Cognitive-Architect-Enablement.git`. You can retrieve this by clicking on the Code button for your repository and copy the SSH URL.
- A sample HTTPS URL for a public Git repository is `https://github.com/IBM/itaa-docs.git`. You can retrieve this by clicking on the Code button for your repository and copy the HTTPS URL.



## Customization

The export utility uses a set of default templates. However, you can change the look and feel of your pages by adding your own customized templates.

??? what about the md files ???

We have used [ejs](https://ejs.co/) as our templating language.

To customize the look and feel of your pages and view the updates pages:
- Copy the appropriate architectural artifact file(s) from the *official_template* folder to the *user_template* one.
  - Note: Do not change the name of the file(s). 
- Modify the content as needed.
- Re-submit the Export request in Cognitive Architect.


💡 Tip: If the GitHub Pages do not reflect your latest updates, clear the cache and refresh.



## Refreshing Your Pages using Command Line Execution
Instead of using the Export utility in Cognitive Architect, you can refresh your GitHub Pages with command line executions.

In a terminal window:
- Run `git clone ...?` to download your repository
  - what's the full command?
  - other options? like downloading the zip file from github or using github desktop
- In the directory where your repository is, run `make venv` to create the python environment
- Run `make serve` to start the docs ??? on your local machine
- Update the docs/*.md files as needed
- When ready, run `make deploy` to deploy the changes
- include step to upload / sync changes back to github repo?



## Reviewing and providing feedback on the documents

We are always looking for feedback.  

- If you have any *suggestions*, please submit a *Pull request* with your suggested changes.
- If you have *general* feedback and comments, please open a *New Issue*.

Your participation is greatly appreciated.
