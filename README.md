# script-bash-push-ghpages

This is a script in bash (push_ghpages.sh) used to automaticly deploy a Jekyll site/blog with third party plugins to GitHub Pages.

## Description

Despite GitHub Pages have a automatic building, it only allow you to use third party plugins that are registered as showed in this list of [suported plugins](https://pages.github.com/versions/). 
So if you wanted to use unregistered third party plugins you should build and deploy the static files manually, as they pointed in their page: [github plugins](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll#plugins): 
"*GitHub Pages cannot build sites using unsupported plugins. If you want to use unsupported plugins, generate your site locally and 
then push your site's static files to GitHub.*"
Thus this script was created to avoid the boring proccess of build and push the static files to the branch gh-pages wich time I upload my personal site/blog in Jekyll.
 
## Getting Started
First you should allow this script to run as a executable in your machine so with Bash/Git Bash run: 

```
chmod u+x push_ghpages.sh
```
after that just exec the file calling it with:

```
. push_ghpages.sh

```
When called without argument the scirpt push with a "Automatic commmit" message.
So if you want to set a commit message just pass it as a argument, like this:

```
. push_ghpages.sh "My commit message goes here"
```


Fist it creates a folder called "PUSH_FOLDER", 
then it's cloned only the branch "gh-pages" from github.
The directory is temporaly changed to "PUSH_FOLDER". 
In the directory it 

### Executing program

* How to run the program
* Step-by-step bullets
```
code blocks for commands
```
