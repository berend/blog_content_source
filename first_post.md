Title: First blog posting
Date: 2013-10-23
Category: blog
Tags: pelican, publishing
Author: berend
Summary: How to set up a blog like this

**Overview**

This a short write up how I created this blog with pelican, markdown and github pages.

Prerequisites:

* Github Account setup with ssh key
* OS: In my examples i use Linux as OS. Should work on Windows and MacOS as well with minor changes
* git installed

**Static blog**

Since a blog isn't really about dynamic content, static pages should be enough to power your blog. One exception is commenting. But make your whole site dynamic just to have comments? Not really. Just a comment provider via javascript/html to your static code and your done. See the comment part for that. 

So, we are still static and use a generator to render all of our html files. I use pelican for that.

Setting up pelican is really easy, there is good documentation. To give you a small outline, here is waht I did.

 First of all, the project structure. I have two git repositories, one for all pelican content and customizations(I will call that from now on "source folder", and one for the final output (called "output folder"). The output is the HTML part you are hosting on github pages, so the repository name HAS to be "github.com/<you_account>/<you_account>.github.io". For the source git, choose any name you want.

 So, two gits: blog_source and berend.github.io.

I have a special folder where I keep all my virtualenv, I created one for my blog there:

    virtualenv pelican

Then activate it:

    source pelican/bin/activate

Install all the needed python packages. In my case I needed pelican and markdown:

    pip install pelican
    pip install markdown

Move to your output directory.
I assume, you already created a repository named "<you_account>.github.io". Clone this to the output folder:
``git clone <you_account>.github.io``. All the HTML will be created here. Right now it should be empty.

Then move to your git folder for the pelican source.  Init your blog with
``pelican init``
Now you should have the basic structure in your source, and as well as the default output folder. We are not going to use this one here, so you can delete it. Now lets have a look at the pelican config files. The most basic settings are all there, a complete list can be found here. Edit as you wish, if you dont like sany lines of that default config just comment out the line.

Make sure you change the output folder to your outputfolder where you just inited the git repo.

That about all for the basic setup. You can now create your articles in /content/, generate the output with pelican and then push the current output to the master branch on github.

**Markdown**

I use markdown as markup language. Pelican supports others, at least REST. But Markdown is widely known. I do know from some personal project and github as well.


**Hosting on github**

OK, having your own top level domain seems cool, but the administration overhead is just too much me. But feel free to host your project on any webserver you want. Since you only have to deal with static pages, there should not be much trouble. No database, no scripting language, etc. Just use FTP in stead of git to bring the current content online.

When you hot your blog on github, you can use all the power of github, you automatically have an issue tracker, other people can collaborate, make suggestions, fix typos, even write own article and send them to you - all via git. And you get to learn some parts of git or github, you might not have encountered elsewhere.

**Comments**

Comments are the only part that should be dynamic on a blog. If you dont want any comments, just skip this part. I found two comment providers. First is Disqus, second is Google+. Disqus is already integrated in pelican, just setup an account at disqus and enter the account name in your pelican.conf.

Setting up the google+ comment connection is a bit harder. It works like this. Here is a blog entry with intructions how to do it. Since many people don't want to comment via Google+ or don't want a Google+ Account at all, I will stick to disqus. (Fun fact: Disqus is written in python and one of the largest Django Websites out there).

**Themes**

Right now you are using the default template for your blog. You don't have to. there is plenty of material out there you can easily use. I will write up later how to do that. Right now I just want to bring this online.

** Including code examples **

    :::python
    import test
    print("this is a test")

By identing code with 4 spaces or tab pelican and markdown will do the rest. Syntsax highlighting can be done by prefixing the code with ``:::python`` or any other supported language. The example above looks like this in the source:

    ____:::python
    ____import test
    ____print("this is a test")

with _ representing a space. Really simple!

** Include images **  
Here is a small image: 

{% img  img/testpicture.png [Testpicture ] %}





