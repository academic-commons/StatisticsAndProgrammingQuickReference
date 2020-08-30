---
layout: page
title: How to setup this website on your local machine?
exclude_from_search: true
---

# How to setup this website on your local machine?

------------------------------------------------------

Once you complete setting up local instance of this website, you will be able to **host this website, access it and modify it** on your local machine. 

Prerequistes to setup locally:
- Create Github Account [here](https://github.com/join?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home).
- Install Github Desktop using [this](https://desktop.github.com/).
- Install Jekyll for your Operating System [here](https://jekyllrb.com/docs/installation/#guides).

Follow the steps to setup website locally:

**Step 1**:  Fork this <b><a href = "https://github.com/academic-commons/StatisticsAndProgrammingQuickReference" target="_blank">repository</a></b> on your local machine.

![fork](fork.png)

**Step 2**: After forking the repository to your github account, clone it to your machine using Github Desktop.

![github_desktop](github_desktop.png)

**Step 3**: After cloning it to your local machine, navigate to the folder where you cloned the repository.

![repo](repo.png)

**Step 4**: Enter the docs folder and open a terminal window. For windows open powershell terminal by holding shift key and right clicking in the explorer.

![powershell](powershell.png)

**Step 5**: Once the terminal opens enter the following command, **bundle update**

![bundle_update](bundle_update.png)

**Step 6**: Next run the following command, **bundle exec jekyll serve --watch**

![web_server](web_server.png)

**Step 7**: Open the server address mentioned in the console.

![success](success.png)

**Step 8**: You have successfully setup local instance of website

![website](website.png)