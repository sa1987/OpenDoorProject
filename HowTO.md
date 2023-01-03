## Getting Started with the handbook using GitHub

Agape courses are websites that are edited and hosted through GitHub, a web-based service for managing code and collaborating on projects. To start, you'll need a (free) [GitHub account](https://github.com/join).

For a great basic primer on GitHub, check out [Hello World](https://guides.github.com/activities/hello-world/) and the [GitHub Term Glossary](https://docs.github.com/en/github/getting-started-with-github/github-glossary). If you get stuck at any point in the setup process, head to our [community forum](https://community.p2pu.org/c/tech/course-in-a-box/78) and someone can help you out!

This guide is a minimal documentation for building your course using our repository with minimal coding knowledge.

## Required Setup

Once you're logged in to GitHub, the first step of creating a course is to copy ( "fork") the course folder ( "repository") from agape's account to yours. This will make an identical copy of this website and its content in your account library. (Making your course is essentially a matter of editing out our content and customizing it with your own.)

To start, head to [agape project repo](https://github.com/sa1987/OpenDoorProject) and click "Fork" in the top right, or simply click the button below:

[Fork this repository on GitHub](https://github.com/sa1987/OpenDoorProject/fork)

You can edit your course directly through GitHub, which offers a Preview tab above the code editor so you can see how your Markdown edits look before you commit your changes and wait for them to appear live:

If you want to write your text in other software before bringing it into your template, here are a few options to convert your formatting into Markdown before bringing it into your temaplte:

\* [GSuite Tool: Google Docs to Markdown](https://github.com/evbacher/gd2md-html/wiki#installing-docs-to-markdown)

\* [Microsoft Word to Markdown Converter](https://word2md.com/)

\* [StackEdit: a visual Markdown editor](https://stackedit.io/app#)

We used the minimal bookdown [template](https://github.com/rstudio/bookdown-demo) and edited it through R studio, which offers a Visual tab above the code editor so you can see how your Markdown edits look before you commit your changes and wait for them to appear live.

To learn more about setting up the R studio, check out the R studio [guide](https://posit.co/download/rstudio-desktop/).

Before, proceeding with customisation, git client needs to be installed as detailed in the [link](https://happygitwithr.com/install-git.html).

<br>

\## Understanding the Course Template

Once you've forked the course, you'll see the course's guts as a list of folders and file names. This list contains all of the learning content for the course as well as the code that holds it all together. This guide will always tell you exactly where to look to update different parts of your course, so you don't need to read or memorize this section in order to proceed.

\<br\>

\#### Directory layout explanation

You can read more about the Bookdown package and it's application in this [link](https://bookdown.org/yihui/bookdown/).

\`\`\`

📁 \_data - course metadata

📁 \_includes - html for page components

📁 \_layouts - html for various page layouts

📁 \_sass - styling code

📁 css - more styling code

📁 fonts - font files (including icons!)

📁 img - image files

📁 js - JavaScript for interactive components of the site

📁 modules - folder for the actual course content

.gitignore - a git file (for keeping this directory tidy)

404.html - error text that appears on broken links or nonexistent pages

CNAME - use for setting custom domains

Gemfile - used by jekyll/GitHub pages

LICENSE - Course-in-a-Box is licensed under the MIT License (do not edit)

README.md - a text file to introduce and explain the project

\_config.yml - Jekyll/GitHub pages configuration & settings

index.md - landing page content

single-page.md - an example single page of content

\`\`\`

### Markdown Cheatsheet

Check out [Mastering Markdown](https://guides.github.com/features/mastering-markdown/) for learning more about Markdown syntax.

## Homepage

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

## Set the course metadata

#### Set the Course Favicon
You can customize the favicon for your course in 3 steps:
1. Create a favicon using a favicon generator link this [link](https://favicon.io/) 
2. Uploade it to the `images` folder.
3. Update the image file location in the `_output.yml` file 

Current configutaion in the [output.yml](https://github.com/sa1987/OpenDoorProject/blob/main/_output.yml) file is
```
  favicon: "images/agapefavicon.ico"
```
#### Set the Course cover image 
You can customize the cover image for your course in 2 steps:
1. Uploade image to the `images` folder.
3. Update the image file location in the `_output.yml` file

Current configutaion in the [output.yml](https://github.com/sa1987/OpenDoorProject/blob/main/_output.yml) file is
```
  cover-image: "images/agapecover.png"
```
A nice effect of setting description and cover-image is that when you share the link of your book on some social network websites such as Twitter, the link can be automatically expanded to a card with the cover image and description of the book.

#### Configure the toolbar

You can enable, disable and modify the entries on the toolbar by modifying the `_output.yml` file.
Current configutaion in the [output.yml](https://github.com/sa1987/OpenDoorProject/blob/main/_output.yml) file is
```
 twitter-handle: AgapeOpenSci
  facebok-handle: Agape Open-Science
  instagram-handle: Agape.Open.Science
  edit: https://github.com/sa1987/OpenDoorProject/edit/master/%s
    sharing:
        twitter: yes
        facebook: yes
        github: yes
        instagram: yes
```

![Toolbar](https://github.com/sa1987/OpenDoorProject/blob/main/images/toolbarimage.png"toolbar")

#### Set the Course Title + Headline

The name of a course is set by editing the `course.yml` in the `_data/` folder:

[https://github.com/your-github-username/course-in-a-box/blog/gh-pages/\_data/course.yml](https://github.com/your-github-username/course-in-a-box/edit/gh-pages/_data/course.yml)

By default, the information in this file will read:

    title: Course-in-a-Box
    description: An open-source project for creating online courses, built by <a href="https://www.p2pu.org">P2PU</a>
    modules: [tutorial, resources, references]
      favicon: "images/agapefavicon.ico"

-   **Title:** This text appears as the title of the page in your browser.
-   **Description:** This text appears as the headline in the large banner on the course landing page.
-   **Modules:** This list controls the modules that appear in the top menu of your course. (See the [Modules](../modules) section for more information).

Commit the changes when you're finished and refresh your course page after a few minutes to see the edits appear.

<br>

#### Update the Course Description

The `index.md` file in the main folder of the course holds the information that appears on the bottom half of the homepage.

<https://github.com/your-github-username/course-in-a-box/blob/gh-pages/index.md>

    ---
    layout: index
    published: true
    ---

You can leave this text alone (it's called "front matter"---more about that in [Submodules](../submodules)) at the top of the document. Using Markdown formatting, add your content underneath. This is a good place to explain a basic overview of the course material, materials required, or instructions for sign-up.

#### Delete CNAME

Once you've forked the project, you'll need to remove the **CNAME** file that appears in the main list of folders and files. This file is specific to P2PU's web hosting for this tutorial website, and it'll prevent your site from working if you keep it. (If you've already got a custom domain that you want to use for your course, you can edit this instead of deleting it---see [Set a Custom Domain](../../customize/custom-domain/) for more information.)

Click the file to open it:

<https://github.com/your-github-username/course-in-a-box/blob/gh-pages/CNAME>

Once open, click the trash can icon in the upper right side of the code section to delete the file. On the confirmation page, click the green "Commit changes" button to update ("commit") your change and return you to the file list.

<br>

## Designing table of content 
You can edit the format of the TOC by modifying the `_output.yml` file. CSS tags for the TOC is sepreately defined in the `toc.css` file. 

#### Updating the ICON
![Toolbar](https://github.com/sa1987/OpenDoorProject/blob/main/images/toolbarimage.png"toolbar")
You can update the icon by modifying image and image link as same as updating course cover image by updating img src link.
```
before: |
        <li><a href="./">AGAPE: An introductory course to open science for early career researchers</a></li>
        <li class="toc-logo"><a href="./"><img src="images/agapecover.png"></a></li>
```
#### Updating the google analytics configuration
You can set up your google analytics configuration by modifying the `google_analytics.html` file in the assets folder.

Default configuration of the agape course can be seen [here](https://github.com/sa1987/OpenDoorProject/blob/main/assets/google_analytics.html).

#### Your course is now live!

You can view it by going to

<https://your-github-username.github.io/course-in-a-box/>

Note: it can take between 2--20 minutes for your course to show up for the first time.
