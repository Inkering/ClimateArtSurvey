---
title: "How to Add an Artist"
layout: PostLayout
date: 2021-2-20
---

We can add new artists to the survey by creating new markdown files:

1. Make a file for each artist in the `artists` folder.
2. Add an image into `.vuepress/public` for each artist. (Shows up on the front page and on their profile)
3. In the new markdown file, add to the top:

    ```
    ---
    title: "First Last"
    layout: PostLayout
    date: 2021-02-20
    img: "/image.jpg"
    ---
    ```
4. Type anything in the markdown file, woo!