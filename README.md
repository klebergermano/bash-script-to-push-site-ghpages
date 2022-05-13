# push-ghpages-script-sh

A script (push_ghpages.sh) used to automatically deploy a [Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll) website/blog with third party plugins to GitHub Pages.

## Description

Despite GitHub Pages have a automatic building, it only allow you to use third party plugins that are in their [suported list](https://pages.github.com/versions/). 
So if you wanted to use unregistered third party plugins you should build and deploy the static files manually, as they pointed in their page: [github plugins](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll#plugins): 
"*GitHub Pages cannot build sites using unsupported plugins. If you want to use unsupported plugins, generate your site locally and then push your site's static files to GitHub.*"
Thus this script was created to avoid the boring proccess involved in this kind of push.

##What this script does is:
Default names of the folders:
BUILD_FOLDER=**'_site'**
PUSH_FOLDER=**'_site_ghpages'***

1. It creates a folder with the seted name in PUSH_FOLDER. / Clean it if the folder alredy exists;
2. Change the directory to the PUSH_FOLDER (cd $PUSH_FOLDER);
3. Clone only the remote branch gh-pages of GitHub to PUSH_FOLDER;
4. Copy all the content of the BUILD_FOLDER to the PUSH_FOLDER;
5. Add all the files of PUSH_FOLDER in the local branch gh-pages, commit and push to the remote gh-pages;
6. Go back to the previouly directory. 


 
## Getting Started
To use it make sure of:
- Ignore the BUILD_FOLDER and the PUSH_FOLDER in the .gitignore file; 
- Already have a empty branch called "**gh-pages**" created in your repository. (After use the script this branch should have only the static files of the build folder)

To execute the script first you should allow it to run as a executable in your machine, to do so, with Bash/Git Bash run: 

```
chmod +x push_ghpages.sh
```
After that just run the file calling:

```
. push_ghpages.sh

```
When called without argument the scirpt push with a '*Automatic commmit*' message.
So if you want to set your commit message just pass it as a argument, like this:

```
. push_ghpages.sh "My commit message goes here"
```

If you have any problem while execute, just delete the PUSH_FOLDER, empty the remote gh-pages and let the script rebuild e push the content.

Also enter the **PUSH_FOLDER** ```cd my_push_folder_directory``` and run a ```git branch``` to check if it have <ins>ONLY</ins> the branch **gh-pages**, if it have a master branch or any other, delete it.
