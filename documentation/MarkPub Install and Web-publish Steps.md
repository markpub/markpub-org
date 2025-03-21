# MarkPub Install and Web-publish Steps 

MarkPub is generates HTML files from Markdown files. (It is a static web-site generator.)

MarkPub can help publish the HTML files to the web by installing instructions that GitHub and Netlify can run automatically.

These instructions yield a GitHub Pages published static website.
### Assumptions and pre-requisites:

These instructions assume the following:
- The primary goal is to build a static website from a collection of Markdown files, and publish that site on the web.
- The Markdown documents are in an existing GitHub repository.  
- Web publishing is hosted by GitHub Pages (or Netlify, see below).

### Prerequisites for installation:  

- Python3 (Version 3.12 or higher) installed.  
- Facility with using a command-line or Terminal app.  
- Know how to use a GitHub repository, and  
- Know how to deploy GitHub Pages, or  
- Can get help with using GitHub and GitHub Pages from someone or some place.  

## Basic installation and use  

Assuming the local folder name, and the GitHub repository name of the Markdown collection, is "myDocumentCollection" these commands initialize and web-publish those documents to a GitHub Pages hosted website.

**Install MarkPub**:
```shell
cd /to/some/work/directory
pip install markpub
```

**Initialize the document collection**:
note: prior to initialization, the `myDocumentCollection` folder must be a local copy (“clone”) of an existing GitHub repository.
```shell
markpub init /full/path/to/myDocumentCollection
```

MarkPub initialization issues terminal prompts for:  

- Website title: "My Document Collection"
- Author: "Your name or names"
- Git repo: github.com/YourGitHubAccountName/myDocumentCollection  

**Web-publish the collection as a GitHub Pages website**:  

```shell
cd /full/path/to/myDocumentCollection
git commit -am "MarkPub installation updates"
git push
```

Log into GitHub, and for this repository's "Pages" settings, set "Build and deployment" "Branch" to "gh-pages" in the drop-down menu, and select "Save".
 - Saving that setting triggers a "pages build and deployment" workflow under the "Actions" tab  
 - Select the repository's "Actions" tab;
 - when the "pages build and deployment" workflow is finished (shows a green checkmark) select that workflow;
 - from the "pages-build-deployment" graph select the green checkmark
          "deploy" link to see the deployed website.
 - when completed the website is available at:  
  <https://YourGitHubAccountName.github.io/myDocumentCollection>  
  
**Web-publish using Netlify**: For Netlify deployment, MarkPub installs a `netlify.toml` configuration file during initialization. You can use this to web-publish your site using [Netlify](https://netlify.app), instead of GitHub Pages.
  
### Configuration  options:  

Some website configuration details are specified in a separate file. For these instructions the file has this name:  `myDocumentCollection/.markpub/markpub.yaml`  

Edit this file to set or change:  
- Site title  
- Author names  
- License  
- Number of recent changed pages to show  
- Git forge information  

Other site-wide settings include:  
- name of the Markdown page used as the website sidebar
- list of Markdown pages that do not have Edit buttons  
- list of directories in the repository that will not appear on the website  

