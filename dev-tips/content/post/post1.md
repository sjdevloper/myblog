---
title: "Building GitHub Page Blog"
date: 2022-01-12T12:05:23-08:00

---

## Install hugo

- (mac)
  - Brew install hugo

## Create two repositories on GitHub and Make them public
- sjiang20.github.io (going to be used as URL)
- Blog

## Clone Blog repositories to local
- Inside of Blog, create,RUN
  - hugo new site dev-tips
- Inside of dev-tips, go directly to themes
- Choose one of the favorite Themes from HUGO official website
  - git clone the Themes from HUGO official website to themes
- Open up config.toml
  - Change baseURL = "https://sjiang20.github.io/ "
  - Change title ="The Simple Engineer Blog"
  - Theme= "contrast-hugo"
- Go back to dev-tips
- - Run "hugo server"
- Web server is available at http://localhost:1313/
- Still Inside of dev-tips, run
  - hugo new post/post1.md
  - Open up this file, then change the titile, and adding some contents(Don't forget to delete Draft=True)

## Clone simpledevblog.github.io repositories to local
- Inside of thesimpledev-tips.github.io
  - Git checkout -b main
  - Touch README.md
  - Adding it to main branch
    - git status
    - git commit -m "adding readme"
    - git push origin main

## Go back to Blog repository
  - Run git submodule add -b main https://github.com/sjiang20/sjiang20.github.io.git public
  - Run hugo server to check the updates
  - Build code in Blog repository
    - hugo -t smol
  - Going to Public fold
    - git remote -v
    - git status
    - git add .
    - git commit -m"init"
    - git push origin main

## Back to the github website
- Go to setting
- Scroll down to the GitHub Pages
- Deploy the website https://sjiang20.github.io
