---
layout: post
title: "Blogception : Create a blog using Jekyll and Github pages - Part 2 : Write your first post"
author: Jeremy Lempereur - o0Ignition0o
---

Blogception is a series of blog posts on how to create a blog... and posts.

As part of the [content-o-tron](https://github.com/rust-community/content-o-tron) initiative, we're committed to help each member of the community and each newcomer to share their story using rust.
This means empowering everyone to write blog posts in order to share feedback with the world.

One of the main issues I've faced as I was trying to write blog posts (besides choosing a topic, and suffering the [impostor syndrome](https://en.wikipedia.org/wiki/Impostor_syndrome); feeling I'm not goot enough to write, or that my experiences are not worth sharing), was the physical setup:

- Should I setup a CMS ? 
- Do I really have to learn _insert_framework_name_here_ just in order to write articles ?
- Will I have to be mindful of HTML / CSS while I only want to write plain sentences ?

So I looked and found a couple of tools that helped me setup my blog. This is a several parts howto to spare you the trouble :) 

In the [first part]({{ "/2018/05/10/blogception-create-blog-jekyll-github-pages-part-1.html" | prepend: site.baseurl }}), we check the requirements in order to setup and run the blog locally, and we run our blog for the first time.

In the second part, we edit the global site configuration, and write our first blog post.

The entire source code of the blog (and its contents) can be found on [a Github repository](https://github.com/o0Ignition0o/blog). Feel free to fork it, edit it, and use it for your own purposes !

## 1. Edit the global configuration

Now that the blog is setup and running locally on your computer, it's time to edit it so it will be yours !

The global configuration file, _config.yml can be found [at the root directory](https://github.com/o0Ignition0o/rust-lang-blog-boilerplate/blob/master/_config.yml)  of the project.

Let's go through each of the settings together, using this blogs configuration as an example :

```yml
# Site settings
title: Jeremy Lempereur # This is the blog name
description: Mainly blogging about Mozilla, Rustlang, and perhaps some other open source related stuff. # A basic description for the blogs purposes
baseurl: "" # We'll use it in part 3 of this series
url: "https://blog.jeremylempereur.com" # This will also come in handy in part 3 of this series
logo: "https://avatars2.githubusercontent.com/u/9465678?s=460&v=4" # This one is used as blog logo (right now it's my profile picture)
twitter_username: o0ignition0o # Your twitter handle
github_username: o0Ignition0o # Your github handle

```

These settings will come in handy on the html templates, in the [header page](https://github.com/o0Ignition0o/rust-lang-blog-boilerplate/blob/master/_includes/header.html). 
As an example, this is the generated code of this blogs header:

```html
<!-- _layouts/layout.hyml -->
<a class="site-title" href="{{ site.baseurl }}"><img id="site-logo" src="{{ site.logo }}"/> {{ site.title }}</a> 
```

This template uses the baseurl (which is empty), and the logo we configured a couple of minutes ago. 

As you can see, variables can be injected by wrapping {\{ and }\} tags around a variable. You can add your own, and use it in the html templates you define.

<!> Note that you don't have to restart the jekyll server when editing css, markdown and html files, but you do have to restart the server when you edit the configuration <!> 

As a quick reminder, you can start your server by running ``` bundle exec jekyll serve ``` in the root directory.

Take a bit of time to play around with the _includes and _layouts directory, as well as the index.html file in order to customize the way your blog will render. Once you're satisfied with the results, we can proceed to the next part.

## 2. Let's write our first blog post !

I probably wouldn't be able to build a guide as thorough as the official [Jekyll documentation](https://jekyllrb.com/docs/home/) which is pretty awesome, go check it out !

Here are a couple of key takeaways you can use to start writing your blog post right now : 

- Create a file in the _posts directory
- The file name does matter, and will resolve to the blog post url (2018-05-11-test-blog.md will resolve to /2018/05/11/test-blog.html)
- A markdown file starts with a Fonts matter block, which helps you define meta data for your post : 

```markdown
---
layout: post
title: "Blogception : Create a blog using Jekyll and Github pages - Part 2 : Write your first post"
author: Jeremy Lempereur - o0Ignition0o
---
```

[Markdown rules](https://guides.github.com/features/mastering-markdown/) apply, as well as a couple of [jekyll tricks](https://jekyllrb.com/docs/posts/) in order to create really cool content.

For example, you can write something in *italic* like this, you can write in **bold** like that. 

## This is an h1 (big) title

# This title is a bit smaller

- This is a list item
- This is an other list item

Visit [https://guides.github.com/features/mastering-markdown/](https://guides.github.com/features/mastering-markdown/) to get more information ! 

## 3. Contents

This blog series focuses on the technical setup of a blog. 

If you're wondering about how to write, know that the Rust Community effort is here to help you blog on your journey. The community provides mentoring, proofreading, and helps you through each step of the writing process.

If you've come this far, you are more than ready to write your first blog post ! :)

Here's an amazing guide of how to structure your blog post, and a couple of key points you want to consider before writing : 

[https://github.com/rust-community/content-o-tron/blob/master/guides/blog_post_template.md](https://github.com/rust-community/content-o-tron/blob/master/guides/blog_post_template.md)

Find out more about the rust community and the [content-o-tron effort](https://github.com/rust-community/content-o-tron), and come have a chat with us on [Gitter](https://gitter.im/content-o-tron/Lobby) or on the IRC [#rust-content](https://kiwiirc.com/client/irc.mozilla.org:+6667/#rust-content) channel ! 

## Conclusion

Congratulations, you have succesfully configured your blog, and written your first post ! 

In the [previous article]({{ "/2018/05/10/blogception-create-blog-jekyll-github-pages-part-1.html" | prepend: site.baseurl }}), we figured out how to install the requirements, and how to setup our local jekyll blog.

In this article, we figured out how to edit the configuration, and how to write our first blog post together.

In the next article, we will check out how to publish our blog on github pages, and how to setup a domain name so we can share a cool link to our brand new blog !

If you have any question, run into an issue, see a typo, want to show me your first blog post, or just wanna chat, please send me a DM on [twitter]({{ site.twitter_username | prepend: "https://twitter.com/" }}), or [open an issue](https://github.com/o0Ignition0o/blog/issues/new) on the blog repository, I would be glad to have a chat with you ! 