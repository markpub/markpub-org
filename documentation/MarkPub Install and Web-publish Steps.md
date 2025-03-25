# MarkPub Install and Web-publish Steps 

MarkPub generates HTML files from Markdown files. It is a [static site generator](https://en.wikipedia.org/wiki/Static_site_generator).

MarkPub helps publish the HTML files to the web by installing automation files for GitHub Pages and Netlify. When you enable the automation, the site will be regenerated automatically by GitHub or Netlify when files are updated.

The following instructions yield a static website published via GitHub Pages.

### Assumptions and pre-requisites

These instructions assume the following:

- The primary goal is to build a static website from a collection of Markdown files, and to publish that site on the web.
- The Markdown documents are in an existing GitHub repository.  
- Web publishing is hosted by GitHub Pages (or Netlify, see below).

### Prerequisites for installation

- Python3 3.12 or higher installed.  
- Comfort using command-line or Terminal applications.  
- Basic GitHub knowledge (repository management).
- GitHub Pages deployment experience, or 
- Can get assistance with GitHub/GitHub Pages.  

## Basic installation and use  

Assuming the local folder name, and the GitHub repository name of the Markdown collection, is "myDocumentCollection" these commands initialize and web-publish those documents to a GitHub Pages hosted website.

**Install MarkPub**:

```shell
cd /to/some/work/directory
pip install markpub
```

**Initialize the document collection**:

Note: prior to initialization, the `myDocumentCollection` folder must be a local copy (“clone”) of an existing GitHub repository.

```shell
markpub init /full/path/to/myDocumentCollection
```

MarkPub initialization will ask you for:  

- Website title: "My Document Collection"
- Author: "Your name or names"
- Git repo: github.com/YourGitHubAccountName/myDocumentCollection  

**Web-publish the collection as a GitHub Pages website**

```shell
cd /full/path/to/myDocumentCollection
git commit -am "MarkPub installation updates"
git push
```

Log into GitHub, and for this repository's "Pages" settings, set "Build and deployment" "Branch" to "gh-pages" in the drop-down menu, and select "Save".

- Saving that setting triggers a "pages build and deployment" workflow under the "Actions" tab  
- Select the repository's "Actions" tab;
- when the "pages build and deployment" workflow is finished (shows a green checkmark) select that workflow;
- from the "pages-build-deployment" graph select the green checkmark "deploy" link to see the deployed website.
- when completed the website is available at:  
  <https://YourGitHubAccountName.github.io/myDocumentCollection>  
  
**Web-publish using Netlify**

For Netlify deployment, MarkPub installs a `netlify.toml` configuration file during initialization. You can use this to web-publish your site using [Netlify](https://netlify.app), instead of GitHub Pages. From your Netlify dashboard, select "Add new site" and "Import an existing project". Netlify will load the repository and run MarkPub automatically.
  
### Configuration  options

Some website configuration details are specified in a separate file, `markpub.yaml`. For these instructions the file has this name:  `myDocumentCollection/.markpub/markpub.yaml`  

Edit this file to set or change:

- Site title  
- Author names  
- License  
- Number of recently changed pages to show  
- Git forge information  

Other site-wide settings include:

- name of the Markdown page used as the website sidebar
- list of Markdown pages that do not have Edit buttons  
- list of directories in the repository that will not appear on the website  

