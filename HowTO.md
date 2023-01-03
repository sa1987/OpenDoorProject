## Getting Started with the handbook using GitHub

Agape course is website that is hosted through GitHub, a web-based service for managing code and collaborating on projects. To start, you'll need a (free) [GitHub account](https://github.com/join).

The pre-requisite is a minimal knowledge of the R and github. For a great basic primer on GitHub, check out [Hello World](https://guides.github.com/activities/hello-world/) and the [GitHub Term Glossary](https://docs.github.com/en/github/getting-started-with-github/github-glossary). If you get stuck at any point in the setup process, head to our [community forum](https://community.p2pu.org/c/tech/course-in-a-box/78) and someone can help you out!

This guide is a minimal documentation for building your course using our template with minimal coding knowledge. The authors are ametuer coders hence this may not be the most effecient code and may have errors.


Designing of the course is primarily guided by two available templates:
1. [Bookdown guide](https://bookdown.org/yihui/bookdown/)
2. [rstudio4edu](https://rstudio4edu.github.io/rstudio4edu-book/index.html) and edited it through R studio, which offers a Visual tab above the code editor so you can see how your Markdown edits look before you commit your changes and wait for them to appear live. You cannot edit your course directly through GitHub.
Here, this guide provides only minimal information on the customization. For more information on the structure of the bookdown and the template, please refer to the aforementioned links.

You can read more about the Bookdown package in this [link](https://bookdown.org/). 

To learn more about setting up the R studio, check out the R studio [guide](https://posit.co/download/rstudio-desktop/).

Before, proceeding with customisation, git client needs to be installed as detailed in the [link](https://happygitwithr.com/install-git.html).

Once you successfully configure the R studio and git client, we can move to the customisation.

## Required Setup

Once you're logged in to GitHub, the first step of creating a course is to copy ( "fork") the course folder ( "repository") from agape's account to yours. This will make an identical copy of this website and its content in your account library. (Making your course is essentially a matter of editing out our content and customizing it with your own.)


### Copy this template

To start, head to [agape project repo](https://github.com/sa1987/OpenDoorProject) and click "Fork" in the top right, or simply click the button below:

[Fork this repository on GitHub](https://github.com/sa1987/OpenDoorProject/fork)

### OR 

Login to your github account and navigate to the agape [repo](https://github.com/sa1987/OpenDoorProject). Click the green "Use this template" button above.  Choose a descriptive name for your repo based on your content. (Unlike when you fork a repo, you get to choose the name. If you change your mind before you do any work, delete your new repo and start over.)

### Set up GitHub Pages

1. On the home page of your repo, click Settings. Scroll down to the GitHub pages section and change **Source** to **master branch /docs folder**.  Above the **Source** line, a bar will appear with your book's URL. The bar will initially be blue and indicate that your book is *ready* to be published and will change to green once it is published. Copy the URL. (Note that sometimes there is a delay until your book actually appears at that URL. If it doesn't appear after a few minutes, make a change and commit it to trigger a GitHub Pages build.)

2. Click the gear button near "About" on the home page of the repo and paste your book URL into the **Website** field that appears on the right.

### Clone the repo

Clone your new repo with *File, New Project..., Version Control, Git* in RStudio.

You can see an example of a simple bookdwon template customization in this youtube [video](https://www.youtube.com/watch?v=m5D-yoH416Y)

### Edit some key files
Refer to the next section `Understanding the Course Template` for more details
<br>
### Render the book
Once you complete the editing
1. Install **bookdown** with `install.packages("bookdown")`. If you already have it, update to the [latest version](https://CRAN.R-project.org/package=bookdown).

2. Render locally with `bookdown::render_book("index.Rmd")`.

3. Use `browseURL("docs/index.html")` to view your book locally (or just open `index.html` in a browser).

4. If it looks good, commit and push all changed files to GitHub. 

(You will need to repeat steps 2 and 4 every time you wish to update the book online.)

#### Your course is now live!

You can view it by going to

<https://your-github-username.github.io/your-repo-name/> and it can take between 2--20 minutes for your course to show up for the first time.

## Understanding the Course Template

Once you've forked the course, you'll see the course's guts as a list of folders and file names. This list contains all of the learning content for the course as well as the code that holds it all together. This guide will always tell you exactly where to look to update different parts of your course, so you don't need to read or memorize this section in order to proceed.

<br\>

#### Directory layout explanation

\`\`\`

📁 \_assets - course metadat configurtaion files

📁 images - image files

.gitignore - a git file (for keeping this directory tidy)

404.html - error text that appears on broken links or nonexistent pages

LICENSE - License file

style.css and toc.css : css configuration for the agape course 

README.md - a text file to introduce and explain the project

\_config.yml - GitHub pages configuration & settings

index.md - landing page content

01-Chapter-1.md - an example of a chapter \`\`\`

### Markdown Cheatsheet

Check out [Mastering Markdown](https://guides.github.com/features/mastering-markdown/) for learning more about Markdown syntax.

### Homepage

The homepage is the part of your course that most people will see first. By default, it shows a large banner and an open space to describe the materials inside the course. This information can be changed at any time without affecting other parts of your course.

<br>

#### Customize the banner

Default [Agape](https://github.com/sa1987/OpenDoorProject/blob/main/images/books.png) banner

Settings for the background of the banner at the top of the page are made in the `header.html` file. If you've uploaded the images into the `images` folder, you can replace the text after `images/` with the file name for the image you want to use. You can also replace the link with an externally-hosted image.

Default [header.html](https://github.com/sa1987/OpenDoorProject/blob/main/assets/header.html) file

    <div class="hero-image-container"> 
      <img class= "hero-image" src="images/books.png">
    </div>

-   `books.png` is the banner that will be used by default

<br> \#### Update the Chapter prefix

The `__bookdown.yml` file in the main folder of the course holds the information on the prefix for each chapter title. The current prefix is Chapter and each chapter. Title of each chapter now appears as Chapter \# chapter_name.

Default [\_bookdown.yml](https://github.com/sa1987/OpenDoorProject/blob/main/_bookdown.yml) file

    chapter_name: "Chapter "

### Set the course metadata

#### Set the Course Favicon

You can customize the favicon for your course in 3 steps: 1. Create a favicon using a favicon generator link this [link](https://favicon.io/) 2. Uploade it to the `images` folder. 3. Update the image file location in the `_output.yml` file

Current configutaion in the [output.yml](https://github.com/sa1987/OpenDoorProject/blob/main/_output.yml) file is

      favicon: "images/agapefavicon.ico"

#### Set the Course cover image

You can customize the cover image for your course in 2 steps: 1. Uploade image to the `images` folder. 3. Update the image file location in the `_output.yml` file

Current configutaion in the [output.yml](https://github.com/sa1987/OpenDoorProject/blob/main/_output.yml) file is

      cover-image: "images/agapecover.png"

A nice effect of setting description and cover-image is that when you share the link of your book on some social network websites such as Twitter, the link can be automatically expanded to a card with the cover image and description of the book.

#### Configure the toolbar

You can enable, disable and modify the entries on the toolbar by modifying the `_output.yml` file. Current configutaion in the [output.yml](https://github.com/sa1987/OpenDoorProject/blob/main/_output.yml) file is

     twitter-handle: AgapeOpenSci
      facebok-handle: Agape Open-Science
      instagram-handle: Agape.Open.Science
      edit: https://github.com/sa1987/OpenDoorProject/edit/master/%s
        sharing:
            twitter: yes
            facebook: yes
            github: yes
            instagram: yes

![Toolbar](https://github.com/sa1987/OpenDoorProject/blob/main/images/toolbarimage.png%22toolbar%22)


#### Update the Course Title, Author and description

The name of a course is set by editing the `index.rmd` in the main folder:

Default [index.Rmd](https://github.com/sa1987/OpenDoorProject/blob/main/index.Rmd) file

By default, the information in this file will read: 

```
title: "AGAPE: An introductory course to open science for early career researchers"
author: "An Agape initiative"
site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib, packages.bib]
biblio-style: apalike
# url: your book url like https://bookdown.org/yihui/bookdown
# cover-image: path to the social sharing image like images/cover.jpg
description: This is an introductory course to open science.
```

- **Title:** This text appears as the title of the page in your browser. 
- **Description:** This text appears while sharing the course link in the social media.

<br>

### About chapters
The `index.md` file in the main folder of the course holds the information that appears on the bottom half of the homepage.

[https://github.com/your-github-username/course-in-a-box/blob/gh-pages/index.md](https://github.com/your-github-username/course-in-a-box/blob/gh-pages/index.md)

Default configuration of the current bookdown template is as follows:
The landing page for the course is index.rmd. You can create more chapters by adding more .rmd files and the naming convention for the chapters will be #-Chapter.Rmd , e.g `01-Chapter-1.Rmd` . Each chapter has a corresponding .rmd file in the main folder. You can add or remove chapters by adding or deleting the .rmd files. You may experience error or format error if you change the filename format. The R bookdown automatically arrange and knit the chapters according to the filenames.
#### Update the content of the chapter 
The structure of the chapter is as follows:

Top of the page has the chapter name
e.g.  `# Open science` in `01-Chapter-1.Rmd` file.
Each paragraph is tagged to the css style block. 
```
::: mainfontFormat
chapter content
::: 
```
Here `mainfontFormat` corresponds to the `mainfontFormat` block in the style.css file. You can also remove the style tag and just add the chapter content, and it will use the default configuration available. 
*You can leave the configuration alone and replace the chapter content, if you are fine with the current style and format of the course or not familiar with the CSS configuration.*

We used the R studio editor to compose the chapter. 
If you want to write your text in other software before bringing it into your template, here are a few options to convert your formatting into Markdown before bringing it into your temaplte:

\* [GSuite Tool: Google Docs to Markdown](https://github.com/evbacher/gd2md-html/wiki#installing-docs-to-markdown)

\* [Microsoft Word to Markdown Converter](https://word2md.com/)

\* [StackEdit: a visual Markdown editor](https://stackedit.io/app#)

#### CSS configuration
You can leave the configuration alone if you are fine with the current style and format of the course. 

<br>

### Designing table of content

You can edit the format of the TOC by modifying the `_output.yml` file. CSS tags for the TOC is sepreately defined in the `toc.css` file.

#### Updating the ICON

![Toolbar](https://github.com/sa1987/OpenDoorProject/blob/main/images/toolbarimage.png%22toolbar%22) 
You can update the icon by modifying image and image link as same as updating course cover image by updating img src link.

    before: |
            <li><a href="./">AGAPE: An introductory course to open science for early career researchers</a></li>
            <li class="toc-logo"><a href="./"><img src="images/agapecover.png"></a></li>

#### Updating the google analytics configuration

You can set up your google analytics configuration by modifying the `google_analytics.html` file in the assets folder.

Default configuration of the agape course can be seen [here](https://github.com/sa1987/OpenDoorProject/blob/main/assets/google_analytics.html).

### Edit README

Once you've completed these steps, update the content of this **README** and add a short description of your project with a link to the book URL.If you liked the template, please give a star :laughing:.
*We would highly appreciate if you mention the agape repo as a reference/source material!*

The configuration details of the quiz and certificate generator will be published separately.


## Reference
Authors referred to multiple how to guides and readme files while preparing this document. Please give a shout out to them too!

Minimal bookdown template by [jtr13](https://github.com/jtr13/bookdown-template)
Setup guide by the [P2PU](https://github.com/p2pu/course-in-a-box)
Yihui's [guide](https://bookdown.org/yihui/bookdown/html.html) for bookdown 
