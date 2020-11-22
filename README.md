# How to update the website

This website is organized in a GitHub repository at www.github.com/engellaboratory.   This is the repository that you're looking at now. `https://github.com/engellaboratory/engellab` hosts all of the *content* that's used to generate the website. This content is turned into the *site pages* that are displayed when you visit `engellab.net` by `hugo`, a static site generator. These site pages are _served_ by a free service called [Netlify](www.netlify.com). Whenever you push an update to the `https://github.com/engellaboratory/engellab` repository, Netlify will see the change and trigger a rebuild of the website automatically. You can also log into Netlify using your GitHub account. If you try pushing a change and can't see it reflected on `engellab.net` after 3-5 minutes, you should check Netlify to see if an error prevented the rebuild.

With that done, all we need to do to edit the website is edit files in the `content/` directory and push to GitHub!

[Here is a great YouTube tutorial playlist](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOnyRlyS-liKL5ReHDcj4G3) that provides an introduction to how Hugo works along with help on the installation process.

## Prerequisites:
#### Homebrew

Homebrew is a package manager for Mac OS. You need to install this only so that you can install `hugo`, which is the program that builds the website. If you're using a new computer, you'll need to install homebrew. Because homebrew is a command-line application, to check if homebrew is installed, open up the Terminal application, and type `which brew`. If you see something like `/usr/local/bin/brew`, then you can skip this step. If nothing gets printed, then proceed.

**Installing Homebrew**

1. Open a web browser and go to https://brew.sh
2. Follow the instructions under the "Install Homebrew" section

#### Hugo

Hugo is a free open-source website builder that takes a set folder and files and creates a website that can be displayed on any browser. Like homebrew, hugo is a command line application. To check if it's installed, open a terminal and type `which hugo`. If nothing gets printed, then proceed.

**Installing Hugo**

1. Open a web browser and go to https://gohugo.io/getting-started/quick-start/
2. Follow the installation instructions

#### Atom

Atom is a text editor with a graphical user interface built by GitHub. It can be used to edit the text files used to build your website. Atom is not a command line application, so you can find it in your Applications folder if it's installed.

If you can't find Atom, then proceed

**Installing Atom**

1. Go to https://atom.io
2. Download the Atom files
3. Drag and drop the application file into your Applications directory.

## Some background on Git

The website is hosted on GitHub and managed using a program called Git. Git lets you manage versions of your website and makes it easy for multiple people to edit the same set of files.

Git is build around the concept of a repository. A Git repository is a folder that can be synced across multiple devices. The `engellab` folder mentioned above is a repository.

GitHub separate from Git, but is offers a resource to remotely host repositories so that there are copies of the files not on your computer.  This is similar to the idea of folders on Dropbox.

There are a few Git commands/functions that you should be familiar with.

**Git clone** downloads a copy of a remote repository (i.e. a repository on GitHub) that _you do not have on your computer_. You will need to clone a repository if you have not already downloaded it on the computer you're using.

**Git fetch** downloads any changes that have happened on a remote repository since you last updated your local copy. It's a good idea to do a **fetch** any time you sit down to work on the website. You can do this on Atom once you've downloaded the website and and opened it using `File > Add Project Folder` by clicking the "Fetch" button in the lower right hand corner.

**Git pull** merged any changes that have been downloaded from the remote repository (i.e. on GitHub) into your local folder (i.e. the folder on your computer). Once you've hit the "Fetch" button on Atom, then if there are changes between your computer's folders and the remote, then the button will change to say "Pull". Clicking that will merge remote changes.

**Git add** also called "staging" on Atom, prepare recent changes to be uploaded to the remote repository. Any time you change a file on your computer and save it, you should see the file come up in the "Unstaged Changes" section on Atom's Git tab. If you don't see the Git tab, go to `Packages -> GitHub -> Toggle Git tab`. If this doesn't do anything, make sure you have at least one file open and/or try restarting Atom. Once files have been added or "staged", they are ready to be uploaded to GitHub. Note that you don't need to add all files that you've edited, only the ones that you are done editing. However, it's probably easiest just to Stage All every time your done working.

**Git commit** adds a set of staged changes to the repostories version history. By adding a "commit message" and hitting the "Commit" button, all staged changes will be added to your *local* copy of the repository.

**Git push** copies all of your local commits to the remote GitHub copy of the repository. You can find the Git push button where the "Fetch" and "Pull" button lives on Atom.

This is a lot of information, but here's an easy way to think about it.

*Before you start working on editing the website* always do a **fetch** and **pull**.

*Once you're done working on the website* always do **add**, **commit**, **push**.

If you follow these steps, you shouldn't have any issues with merges. If you have issues with merges, the easiest thing to do is probably to delete you local copy of the repository (abandoning all changes since your last push), re-clone the repository, and make your changes again.

## Downloading the repository  

Note, for all of the commands that begin with `$ `, this means you need to enter it into a command line using the Terminal Mac OS app.

1. Pick a folder to download the website repository into. I use a directory structure like `$HOME/websites/`. If you decide to put the website into another folder, then anywhere you see the `$HOME/websites/`, replace the path of the new directory.

2. Open the terminal, and change directory into the folder you want to use
```
$ cd $HOME/websites/
```

3. Clone the repository (this makes a copy of the repository on your computer)
```
$ git clone https://github.com/engellaboratory/engellab.git
```

4. Change directory into the folder you just downloaded.

```
$ cd engellab
```

## Editing the website

To edit the website, I recommend using Atom. Once it's installed from atom.io, you can open your website by going to `File -> Add Project Folder` and navigate to the folder where you cloned the website in the previous section.

If you want to see what edits to the website will look like after you've made your changes, you can use `hugo server` to render the website locally (i.e. on your computer) and see what it will look like when you deploy to GitHub.

To start the `hugo server`, do the following

1. Open the terminal and change directory into the website directory.

```
$ cd $HOME/websites/engellab
```

2. To start **previewing the website locally**, start the hugo server

```
$ hugo server
```

3. Open a web browser and navigate to the following address:

```
localhost:1313
```

FYI - this address is only visible on your computer when you are running `hugo server`. If you close hugo server, the address will not work.

4. **Edit** the website using Atom and check your changes on the web browser. Whenever you save a file, `hugo server` will know and refresh the website for you.

5. When you are done, stop the server by holding `ctrl` and hitting `c`. This will stop the server.

6. To **publish** your changes to https://engellab.net, once the server has been stopped, you need to push your changes to github.

You have two options:

Option A:
Push changes to github using Atom. Here's a video showing how this is done: https://www.youtube.com/watch?v=HZV7OKoD1Hc.
  1. Open the Git tab (in the menu bar, go to Packages > GitHub > Toggle Git Tab)
  2. Select all the changes you'd like to Push (you should see the files in the "Unstaged Changes" section)
  3. Hit "Stage Changes"
  4. Type out a commit message describing the changes
  5. Hit "Commit to master"
  6. Hit the "Push" button on the bottom bar.
  7. Check


Option B:
In terminal, run the following commands. For help, see this document (https://help.github.com/en/github/using-git/pushing-commits-to-a-remote-repository):

```
$ cd $HOME/websites/engellab
$ git add .
$ git commit -m "replace this text with your description of the changes here"
$ git push
```

You're done! You can see changes reflected on the public website within one minute.

### How to add images to the activities slider

Prerequisites: Images for the slider must be cropped to a 5x7 (landscape) aspect ratio. You can do this in Apple Photos by importing the photo, double clicking the thumbnail, and hitting the "Edit" button in the top right corner. From here you will find a crop tool that will let you specify a set aspect ratio of 5x7. Crop the image and then save the cropped image into the folder at `/static/img/people/`.

The activities images are listed in a markdown file: `/content/people/slider.md`. Starting on line 18 of that file, you will see the following text:
```toml
# Slides.
# Duplicate an `[[item]]` block to add more slides.
[[item]]
  title = ""
  content = ""
  align = "center"

  overlay_color = "#555"  # An HTML color value.
  overlay_img = "people/group_photo.jpeg"  # Image path relative to your `static/img/` folder.
  overlay_filter = 0  # Darken the image. Value in range 0-1.

```

To add a new photo, duplicate the `[[item]]` block into the position that you want it to appear in the slider. The `title` text will appear as the caption. Note that the `img` attribute does not need the path to begin with `/static`.

### How to add news sections

If you open the `content/post/` directory, you will find the following structure:
```
content/post/
├── _index.md
├── covid-19-vaccine
│   ├── featured.jpg
│   └── index.md
└── deans-workshop-covid-19
    ├── featured.jpg
    └── index.md
```

As you might guess, each news article is actually a directory with two files in it: `featured.jpg` and `index.md`.

The first thing you should do to create a new story is create a new directory with a 2-4 word name separated by dashes like `science-march`. This name will become the URL of the article, such as `https://engellab.net/posts/science-march/`.

In this directory, you should add your `featured.jpg` image. The `featured.jpg` image is the thumbnail that is displayed on the front page and the larger image on the article page for new stories that are not hosted externally (more on that later). `featured.jpg` does not need to be cropped, unless you are unsatisfied with the way the image is displayed. This image can be either a JPEG or PNG image, but I recommend JPEG because the files are generally smaller.

The bulk of the news article details go in the `index.md` file. The first decision you need to make is if you'd like the article to be hosted on the website or if you'd simply like to provide a link to an external news source.

The content of an externally-hosted article's `index.md` file looks like this:

```yaml
---
title: 'Yale researchers pursuing COVID-19 vaccine based on powerful Yale platform'
subtitle:
summary: The urgent search for a vaccine to protect against COVID-19 is well underway, with a number of experimental gene-based vaccines in various stages of development by biotech companies and academic scientists worldwide.
authors:
- admin
tags:
- Academic
categories:
- Demo
date: "2020-04-29T00:00:00Z"
lastmod:
featured: false
draft: false

external_link: https://news.yale.edu/2020/04/29/yale-researchers-pursuing-covid-19-vaccine-based-powerful-yale-platform

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Placement options: 1 = Full column width, 2 = Out-set, 3 = Screen-width
# Focal point options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
image:
  placement: 2
  caption: ''
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
```

You can simply copy one of the existing `index.md` files in the `/posts` directory and then edit the title, date, link, and summary to your satisfaction. Note, the date of the article must be in the past, otherwise Hugo won't publish the article.

If you would like the article hosted on your website, you need to add all the text and images you would like in the article below the second set of three dashes. To show you what this looks like, I've added a `new-website` article. You can delete this if you like.

The self-hosted article `index.md` file looks like this:
```
---
title: "The Engel Laboratory has a new website by Experimental Design"
date: "2019-05-22"

# Summary. An optional shortened abstract.
summary: ""
image:
  focal_point: "Center"

---

Experimental Design, run by Daniel Burkhardt of New Haven CT, designed the new website of the Engel Laboratory.

[**Click here to visit Experimental Design.**](https://experimentaldesign.io)
```

The article format using Markdown, a popular markup language. You can learn more about Markdown here: https://guides.github.com/features/mastering-markdown/. Markdown supports all kinds of simple formatting options, like lists, links, bolding, images, etc.

Once you save the `index.md` file, you will be able to see the new article at `localhost:1313/posts/article-folder-name` if you have `hugo server` running.

### Adding a lab member

Content for lab members is broken down into two directories.

* `/content/authors` contains the content for each lab member and their individual web page
* `/content/people` contains the content for the `engellab.net/people` page and includes the sliders, job posts, people-cards, etc.

Similar to the articles, the lab members directory is organized into folders.

```
content/authors
├── admin
│   ├── _index.md
│   └── avatar.jpg
├── shuo
│   ├── _index.md
│   └── avatar.jpg
└── yuka
    ├── _index.md
    └── avatar.jpg
```

The first thing to do to add a new lab member is to create a directory in `/content/authors`.

Next, you need to prepare the `avatar.jpg` image that will be used to generate the cards seen on `engellab.net/people`. As such, `avatar.jpg` must be cropped to 1x1 (square) aspect ratio prior to uploading. You can do this in Apple Photos by importing the photo, double clicking the thumbnail, and hitting the "Edit" button in the top right corner. From here you will find a crop tool that will let you specify a set aspect ratio of 1x1. Crop the image and then save the cropped image into the folder at `/static/img/people/`.

Finally, you need to prepare the `_index.md` file. The leading underscore is important here. For most lab members, the `_index.md` file looks like this:

```
---
# Display name
title: Nora Engel, PhD

# Username (this should match the folder name)
authors:
- admin

# Is this the primary user of the site?
superuser: true

# Role/position
role: Associate Professor, Medical Genetics and Molecular Biochemistry

# Organizations/Affiliations
organizations:
- name: Temple University
  url: ""

# Short bio (displayed in user profile at end of posts)
bio: Head of the Engel Lab

interests:
- Sex differences
- Gene regulation
- Early development

education:
  courses:
  - course: Postdoctoral Fellowship
    institution: University of Pennsylvania
    year: 2005
  - course: PhD in Molecular Biology
    institution: University of Buenos Aires
    year: 1997
  - course: University Degree
    institution: University of Buenos Aires, School of Biochemistry

# Social/Academic Networking
# For available icons, see: https://sourcethemes.com/academic/docs/page-builder/#icons
#   For an email link, use "fas" icon pack, "envelope" icon, and a link in the
#   form "mailto:your-email@example.com" or "#contact" for contact widget.
social:
- icon: envelope
  icon_pack: fas
  link: 'mailto:noraengel@temple.edu'  # For a direct email link, use "mailto:test@example.org".
- icon: google-scholar
  icon_pack: ai
  link: https://scholar.google.co.uk/citations?user=sIwtMXoAAAAJ

# Link to a PDF of your resume/CV from the About widget.
# To enable, copy your resume/CV to `static/files/cv.pdf` and uncomment the lines below.
# - icon: cv
#   icon_pack: ai
#   link: files/cv.pdf

# Enter email to display Gravatar (if Gravatar enabled in Config)
email: ""

# Organizational groups that you belong to (for People widget)
#   Set this to `[]` or comment out if you are not using People widget.
user_groups:
- Principal Investigator
---

Dr. Nora Engel is Associate Professor in the Lewis Katz School of Medicine at the Fels Institute for Cancer Research and Dept. of Medical Genetics & Molecular Biology at Temple University in Philadelphia, PA. Nora received her Ph.D. in Molecular Genetics from the University of Buenos Aires School of Biochemistry. Her graduate work focused on transcriptional regulation in cancer. She then pursued a postdoctoral fellowship in the laboratory of Dr. Marisa Bartolomei at the University of Pennsylvania, where she investigated mechanisms of genomic imprinting during embryogenesis in mouse models.

As an independent investigator, Nora continued her studies on how imprinted regions are regulated and how the epigenetic and three-dimensional conformation is disturbed in imprinting disorders.

Currently Nora’s major interest is in how sex differences are established in somatic tissues during embryogenesis, how the sex chromosomes contribute independently to those differences at the transcriptional and epigenetic levels and how these differences are reflected in sex disparities in disease risk and outcomes.
```

You can edit the information here, and it will be reflected in the people cards and on the individual's web page. Content from this page can be copied into other user's `_index.md` files if desired.

Note, the "role" position must be one of the options in the `user_groups` list in the [`/content/people/people.md`](https://github.com/engellaboratory/engellab/blob/master/content/people/people.md) header. If you add a new user and don't see them on `engellab.net/people`, then it's likely that there is a typo in their role.

### Google Analytics

Analytics for the website can be tracked at analytics.google.com using the `engellab@gmail.com` login. A beginner tutorial for Google Analytics can be found here: https://analytics.google.com/analytics/academy/course/6
