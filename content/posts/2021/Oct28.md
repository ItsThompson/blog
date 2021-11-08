---
title: "How I Set Up My Blog with Hugo"
date: 2021-10-28T09:21:01+08:00
showToc: true
description: "Discussing the why and how of creating a blog with Hugo"
draft: false
tags: ["Hugo", "PaperMod"]
categories: Computer Science

editPost:
    URL: "https://github.com/ItsThompson/blog/blob/main/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---

## Why create a blog?

Sharing information has always been a cruitcial part of humans. Whether it be tips and tricks to get cheaper food, videos, and even scientific papers. In the current day and age of information, sharing knowledge is one of the key ways that we can advance. I always found helpful information through blogs and articles. For instance, I have used blogs during my IGCSE revision, during my IB Physics studies, and even for a wide variety of topics in game development.

Because I have begun my final two years in highschool, I have decided my knowledge may be finally useful to the world. It almost feels like paying back for all the knowledge that I have gained through the internet. My hope for this blog is to decrease the barriers of entry and that people can learn something new.

Lastly, this blog will allow me to have the chance of self-reflection and finding my strengths and weaknesses. This can allow me to be able to evaluate my own ideas, emotions, and how I process things.

## How I did it

### Technologies

 - [Github](https://github.com/)
 - [Hugo](https://gohugo.io/)
 - [PaperMod Theme](https://themes.gohugo.io/themes/hugo-papermod/)

 ### The setup:

 1. Create two github repositories. One for development and one for the static assets. The repo that contains your static assets will host the Github Pages for your website.
 2. Download hugo onto your computer. You can read [this quick start guide](https://gohugo.io/getting-started/quick-start/) for more information on how to install hugo.
 2. Clone your source code repository onto your computer. You can do this by typing the following in the terminal: `git clone http://github.com/<Username>/<RepoName>.git`
 3. Create a new hugo site by typing the following in the terminal: `hugo new site <SiteName>`

### Installing the Theme:

1. In the terminal, type ``cd themes``
2. Download the theme by typing ``git clone https://github.com/adityatelange/hugo-PaperMod.git``
3. In order to utilize the theme, we need to go to the config file. Go back to your root folder of this project and open config.toml. Because the theme authors recommended to convert the toml file into yml, I will changed the toml file into a yml file.
4. At the beginning of the file you want to delete all of the contents and copy this in:
```yml
baseURL: "http://<Username>.github.io/"
languageCode: en-us
title: <Title>
theme: hugo-PaperMod
```
5. Important thing to keep in mind is to get the base URL correct. If you are hosting your website slightly differently you may need to change the baseURL.
6. If you would like to preview the site locally you can run the following: `hugo server`
7. This will generate the code and sets up the web server for you to view.


### Adding your first post

1. In the console, type `hugo new post/<PostName>.md`
2. The command will return a location to where the markdown file is generated.
3. When you look at the file, there is the header where the title, date, and draft mode is. This is where you can fidget with the settings to your needs. Under the three dashes is where you can write your post contents.

### Submodule

In the beginning, we created two different repos. We will now add the other repo as a submodule. This will allow us to create a more structured project.
1. In order to do this, we will need to make sure that the production repo is not empty. We can do this by cloning the production repo elsewhere and creating a README.md file.
2. Once we have created a file in the production repo, we can place the repo inside our public folder in our project. To do this we write: `git submodule add -b main`
3. We can generate our static files by typing the command `hugo -t hugo-PaperMod`
4. We then enter into the public folder and push it into github and deploy the github page.

### Configuring the config.yml

#### Significant features:
- Navbar options
- Home-info mode

#### Navbar Options

```yml
menu:
    main:
        - name: Archive
          url: archive/
          weight: 5
        - name: Search
          url: search/
          weight: 5
        - name: Categories
          url: categories/
          weight: 5
```

#### Home-info mode
```yml
params:
    homeInfoParams:
            Title: Thompson's Blog
            Content: "A personal blog exploring the field of mainly Computer Science but also Mathematics, Physics, and Economics."
```