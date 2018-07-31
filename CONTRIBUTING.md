# GDG Baroda Website - Contribution Guide

### Table of Contents

* [Introduction](#introduction)
* [Basic usage and setup](#basic-usage-and-setup)
* [Setup Ruby and Jekyll](#setup-ruby-and-jekyll)
* [How to make changes](#how-to-make-changes)
* [How to write posts](#how-to-write-posts)
* [Writing Pull Requests](#writing-pull-requests)


## Introduction
At GDG Baroda, we believe in openness and community collaboration, and we welcome contributions from everyone. This guide will help you understand what are the basic requirements to make a successful contribution, such that the community and you benefit from it.

Please note that you must strictly adhere to the guidelines provided here, or we will not be able to accept your contributions. __This is to maintain our standards, as well as make it easier to maintain this project.__

This project uses [Jekyll](https://jekyllrb.com/) which is a very popular static site generator, and is easy to use. We chose Jekyll due to its popularity, so that most people can contribute easily and finding documentation is also easy.


## Basic Usage and Setup

#### Setup and Installation
The most basic requirements to start working with us is to have a GitHub account and having Git installed in your local machine. You can learn how to install Git using the following links:

-  [Download and install the latest version of Git](https://git-scm.com/downloads)
- [Set your username in Git](https://help.github.com/articles/setting-your-username-in-git)
- [Set your commit email address in Git](https://help.github.com/articles/setting-your-commit-email-address-in-git)

#### Fork the repository
The next step towards is to *fork* this repository in your own GitHub account. 

1. On GitHub, navigate to the [gdgbaroda/gdgbaroda.github.io](https://github.com/gdgbaroda/gdgbaroda.github.io) repository.
2. In the top-right corner of the page, click the __Fork__ button.

That's it! You just forked the original `gdgbaroda/gdgbaroda.github.io` repository in your own GitHub Account. The fork should be present at `[username]/gdgbaroda.github.io`, where `[username]` is your GitHub username.

----

__FAQ : Why do I need to fork this repository?__

This repository is open source, which means anyone on the internet is able to *read* the contents, but, the *write* access is controlled and is only assigned to the members. Hence, you cannot make changes to the main repository itself. You must create a copy and then submit the changes in the form of a *Pull Request (PR)*. 

Creating a *fork* is basically creating a copy of this repository in your GitHub account, and you have the right to make changes to this *copied* repository (since you are the owner).

---

#### Clone the repository locally 
Since you have a *fork* in your GitHub account, you can now clone the repository to your local machine.

Open up the console or terminal or command line on your machine, and run the following command:

`git clone https://github.com/[username]/gdgbaroda.github.io` where `[username]` is your GitHub username.

It should create a new `gdgbaroda.github.io` directory where you executed the command. Run the following command to change the directory :

`cd gdgbaroda.github.io`

You are now inside the directory created by Git and you can use the folllowing command to check the contents of the directory. They should match is shown here : https://github.com/gdgbaroda/gdgbaroda.github.io.

On MacOS / Linux
```
ls -la
```

On Windows&trade;
```
dir
```

Now, we will add the original repository as a remote so that updates can be received:

```
git remote add upstream https://github.com/gdgbaroda.github.io
```


## Setup Ruby and Jekyll

Jekyll is a program written in Ruby and hence we must install Ruby to get started. Jekyll supports Ruby `2.2.5` or above. 

For MacOS and Linux, please follow [this guide](https://jekyllrb.com/docs/installation/)
For Windows, please follow [this guide](https://jekyllrb.com/docs/windows/)

Once you have setup your environment according to the respective guide for your operating system, you have to run the following command to install Bundler :

```
gem install bundler
```

----
__FAQ: Why do we need to install Bundler?__

Bundler is a RubyGem which allows us to install other ruby gems for each project. RubyGems (when we use `gem install`) installs the gems globally, i.e, common for all projects, which is not the recommended approach. Hence, we use Bundler, which helps us install per-project dependencies easily.

----

Next, go to the directory where we cloned our repository, like this:

```
cd gdgbaroda.github.io 
```
Please note that incase you have changed directories, you will have to get back to where you cloned initally. Usually, closing and opening the terminal again will do it.

Now we need to install the dependencies of this project using bundler. To do so, run:

```
bundle install
```

Once this command has executed, you can run this command to see the website running locally:

```
bundle exec jekyll serve
```

You should see something similar to the following output:

```
Configuration file: /Users/curos/gdgbaroda.github.io/_config.yml
Configuration file: /Users/curos/gdgbaroda.github.io/_config.yml
            Source: /Users/curos/gdgbaroda.github.io
       Destination: /Users/curos/gdgbaroda.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 0.281 seconds.
 Auto-regeneration: enabled for '/Users/curos/gdgbaroda.github.io'
Configuration file: /Users/curos/gdgbaroda.github.io/_config.yml
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

As you can see, you can see the website running at "http://127.0.0.1:4000" and you can check by opening it in your browser. It should show the website similar to https://gdgbaroda.com.

Dont forget to stop the server by pressing `Ctrl+C` in the terminal before moving ahead.

## How to make changes

Assuming you have a working clone locally, its time to make some changes to the project.

First of all, ensure you are in the cloned directory (`gdgbaroda.github.io`). 

### Create a new branch

Let's make sure we are in the `master` branch:

```
git checkout master
```

Also, lets pull all changes that might have been pushed since your last update:

```
git pull upstream master
```

Here, we pulled all the changes from the main repository into your local copy.

Now create a new branch by running the following command:

```
git checkout -b add-post-on-devfest
```
Here, `add-post-on-devfest` is the name of the new branch, and it must directly represent what changes you are trying to make. Consider the following examples:

- add-agile-meetup-post
- fix-images-in-codelab
- fix-facebook-link

Also consider the following example branch names which are __improper__ and __must not__ be used:

- manan
- 1
- manan-2
- fix
- bug
- abc
- add-post
- fix-post
- add

You should see something similar to the following output once the command executes :

```
Switched to a new branch 'add-post-on-devfest'
```

You are now ready to make changes!

### Run Jekyll on watch mode

Jekyll has a special `watch` mode that helps when making changes. When running in watch mode, Jekyll will rebuild the website whenever you make a change to any file. You can run Jekyll in watch mode by running:

```
bundle exec jekyll serve --watch
```

Now the localhost site should update itself whenever you make a change in any of the files! Try editing `index.html`, save it, then refresh the browser.

You can now make changes to the project as you wish.

### Commiting changes

Once you are done with making changes, kill the Jekyll server you're running by pressing `Ctrl+C` and then, you must run the build script by running this: 

```
./build.sh
```

If there are errors at this stage, they must be rectified before proceeding further. 

After testing, you must commit the changes to your repository. To do so, first, add all applicable changed files to staging area:

```
git add _posts/2018-06-01-new-post-on-wtm.md
```

Here, `_posts/2018-06-01-new-post-on-wtm.md` is the filename being added to the staging area. Add all files that you have changes in this way. You can use the following command to see the changes and the staging area:

```
git status
```

You can learn more about the `git add` command by reading [this article](https://www.atlassian.com/git/tutorials/saving-changes).

You can learn more about the `git status` command by reading [this article](https://www.atlassian.com/git/tutorials/inspecting-a-repository).

Once you have added all files that you have changed to the staging area, commit the changes like this:

```
git commit -m "added new post on WTM"
```

Here, _"added new post on WTM"_ is the commit message and it is compulsory to provide one. The message must be descriptive and explain what changes were made. Failing to provide a descriptive commit message may lead to contributions not being accepted.

You can learn more about the `git commit` command by reading [this article](https://www.atlassian.com/git/tutorials/saving-changes/git-commit).

If the commit is successful, you can now push your branch and its changes to your GitHub repository:

```
git push -u add-post-on-devfest
```

Here, `add-post-on-devfest` is the name of the branch you created in the previous steps, and you must use the same name here. Git might ask you for your credentials for your GitHub account, so that it can push changes.

Your changes are now pushed to GitHub and you can see it by going to the repository page!

### Create a Pull Request

You can read the following guide for creating a Pull Request:

https://help.github.com/articles/creating-a-pull-request-from-a-fork/

### Modifying a Pull Request

Once you have submitted a pull request, you can update it by commiting and pushing new changes to the _same_ branch from which you have generated the PR.

For example, assume that you created a PR from the branch 'add-io-post'. Now, if you wish to make changes, you have to do the following: 

1: Checkout the existing branch
```
git checkout add-io-post #change to that branch
```

2: Make required changes

3: Test build, add files, make a commit, then push to the same branch:
```
./build.sh # Do not proceed if this command fails
git add file1.md
git add file2.md
git commit -m "title heading fixed"
git push
```

## How to write posts

Each post _MUST_ be a Markdown (.md) file under the `_posts` directory. You can copy any existing post and remove its content, that is a good starting point.

Each post has a _Front Matter_, which looks like this:
```
---
layout: post
title: "A New Beginning!"
date: 2017-02-12 9:00:00 +0530
categories: ["general"]
tags: ["general", "new"]
author: Manan Jadhav
---
```

It is important to have a front matter in each post, and it should contain relevant information only. This is used by Jekyll to build the website.

Posts are written in Markdown, which you can learn from here: https://daringfireball.net/projects/markdown/basics

### Adding Images 

When you want to use images, they must be downloaded and placed under a subdirectory of the `assets` directory. 

The assets directory is organised according to year-month and the post title. It usually looks like this :

```
assets
|- 2018-07
  |- io-extended
    |- participants_cheering.jpg
    |- io-keynote.jpg
  |- wtm-meetup
    |- speaker-manan.jpg
    |- tensorflow-usage.jpg
|- 2018-08
  |- devfest-2017
    |- keynote.jpg
```

As you can see, the assets are put in a directory with the post name, and that directory is inside another directory that is named according to the month in which the post belongs to. This pattern _MUST_ be followed for all images being added.

It is _MUST_ to use either JPG or PNG images, and the filesize must be less than 250 KB in all cases. 

Directly linking to external images is also _NOT_ allowed.

### Writing Pull Requests

When you create a new Pull Request, your description must follow this template:

[Pull Request Template](https://github.com/SnehPandya18/gdgbaroda.github.io/blob/master/PULL_REQUEST_TEMPLATE.md)
