---
layout: post
title: "Blogception : Create a blog using Jekyll and Github pages - Part 1"
author: Jeremy Lempereur - o0Ignition0o
---

Blogception is a series of blog posts on how to create a blog... and posts.

As part of the [content-o-tron](https://github.com/rust-community/content-o-tron) initiative, we're committed to help each member of the community and each newcomer to share their story using rust.
This means empowering everyone to write blog posts in order to share feedback with the world.

One of the main issues I've faced as I was trying to write blog posts (besides choosing a topic, and suffering the [impostor syndrome](https://en.wikipedia.org/wiki/Impostor_syndrome); feeling I'm not goot enough to write, or that my experiences are not worth sharing), was the physical setup:

- Should I setup a CMS ? 
- Do I really have to learn _insert_framework_name_here_ just in order to write articles ?
- Will I have to be mindful of HTML / CSS while I only want to write plain sentences ?

So I looked and found a couple of tools that helped me setup my blog.

In the first part, we check the requirements in order to setup and run the blog locally, and we run our blog for the first time.

The entire source code of the blog (and its contents) can be found on [a Github repository](https://github.com/o0Ignition0o/blog). Feel free to fork it, edit it, and use it for your own purposes !

# 1. Prerequisites

In order to run a local version of the blog on your computer, and in order to publish it online, you will need a couple of tools : 

- Git, which you can [download and install here](https://git-scm.com/downloads)
- Ruby, which you can [download and install here](https://www.ruby-lang.org/en/downloads/)
- A Github.com account, which you can [setup here](https://github.com/join)

Don't worry, you won't actually need to learn and write Ruby, The blog articles will be written in [Markdown](https://guides.github.com/features/mastering-markdown/), and once you've setup the HTML and CSS layout of your blog, you won't have to worry about it anymore. You can even leave the layout of the blog as is, and it will look exactly like the Rust Programming Language Blog, and mine ;).

What you do need to know a bit, is how to use Github and git, since it's out of the scope of this series. A great quickstart on how to use git and github in an Open Source context can be found on [channelcs blog](https://channelcs.github.io/best-practices-in-a-collaborative-environment.html).

# 2. Get the blog boilerplate

You didn't expect me to let you down and let you start from scratch, did you ? :)

Here's a link to the [boilerplate](https://github.com/o0Ignition0o/rust-lang-blog-boilerplate) you want to clone, in order to start setting up your blog: [https://github.com/o0Ignition0o/rust-lang-blog-boilerplate](https://github.com/o0Ignition0o/rust-lang-blog-boilerplate)

This is a fork from the [The Rust Programming Language Blog
](https://blog.rust-lang.org/), where I removed the articles and most of the content.

The boilerplate contains layouts, a bit of styling, and a sample article we're going to modify to write our first post.

But first we need to fork, clone and setup the repository.

<!> Before we dive in with the command line, there are 3 kinds of lines : 

```bash
$ this is a command we are going to enter
# This is a commentary, do not copy it :)
this line does not start with a $ sign
this is the expected output of the command line.
```

Ok let's go !

First, [follow this guide](https://help.github.com/articles/fork-a-repo/) in order to fork the boilerplate repository to your own Github account.

Then you can clone the repository into one of your local folders : 

```bash
$ git clone git@github.com:<your_github_handle>/rust-lang-blog-boilerplate.git
Cloning into 'rust-lang-blog-boilerplate'...
remote: Counting objects: 57, done.
Receiving objects:  22% (13/57)   (44/44), done.
remote: Total 57 (delta 17), reused 50 (delta 10), pack-reused 0
Receiving objects: 100% (57/57), 31.83 KiB | 378.00 KiB/s, done.
Resolving deltas: 100% (17/17), done.
```

Now you have the new repository, and we can set it up and run the blog locally ! In the same command line, let's go to the boilerplate directory, and install the ruby requirements for jekyll : 

```bash
$ cd rust-lang-blog-boilerplate
$ gem install bundler jekyll # This will install global requirements
Successfully installed bundler-1.16.1
Parsing documentation for bundler-1.16.1
Done installing documentation for bundler after 5 seconds
Successfully installed jekyll-3.8.1
Parsing documentation for jekyll-3.8.1
Done installing documentation for jekyll after 1 seconds
2 gems installed
```
Now that the global requirements have been installed, let's install the blog local requirements. 

If you get any error while running the "gem install" command, this means ruby did not install correctly, or the executable is not in your PATH, you might want to log out and back into your session and make sure ruby got installed successfully.

```bash
$ bundler install # Install the blog requirements
[...] Using github-pages 92
Bundle complete! 2 Gemfile dependencies, 53 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed. 
```
The blog requirements have been installed, let's run our blog for the first time !

```bash
$ bundle exec jekyll serve # Run the blog locally
[...]  Server address: http://127.0.0.1:4000/rust-lang-blog-boilerplate/
  Server running... press ctrl-c to stop.
```
Now visit [http://127.0.0.1:4000/rust-lang-blog-boilerplate/](http://127.0.0.1:4000/rust-lang-blog-boilerplate/) to see your blog in action !

![Our first blog is running !]({{ "/images/first_run.png" | prepend: site.baseurl }} "First blog run")

Congratulations, you have successfully forked, cloned and setup your first blog ! 

In the next article, we'll figure out how to edit the configuration, and we'll write our first blog post together !

If you're really eager to do it, have a look at the [_config.yml](https://github.com/o0Ignition0o/rust-lang-blog-boilerplate/blob/master/_config.yml) file in the boilerplate, as well as the [README.md](https://github.com/o0Ignition0o/rust-lang-blog-boilerplate/blob/master/README.md) file, and the [dummy blog post](https://github.com/o0Ignition0o/rust-lang-blog-boilerplate/blob/master/_posts/2018-05-10-blog-boilerplate.md) :)

If you have any question, run into an issue, see a typo, want to show me your first blog post, or just wanna chat, please send me a DM on [twitter]({{ site.twitter_username | prepend: "https://twitter.com/" }}), or [open an issue](https://github.com/o0Ignition0o/blog/issues/new) on the blog repository, I would be glad to have a chat with you ! 