---
layout: post
title:  "How to Create a Free Webpage (Sort of)"
author: TJ
categories: [ Technology, Tutorials ]
image: assets/images/FirstGithubPage/FirstGithubPage.png
featured: true
---

Today we're going to look at how to create a simple static web page hosted for free on github.  So, what is a static website? A static website is a website that contains only fixed content. No database and no server-side scripting. In the past this would really restrict us to basically having an image that can be viewed across the web, but now we can do some pretty neat things with CSS and Javascript.

It should be noted that this tutorial presents a way to build your own static site by using tools such as HTML, CSS, and Javascript. If you are looking for a free way to create a drag-and-drop solution, I will have a future tutorial on how to create a static site on Google Sites. Trust me, though - if you take that approach, there will come a time where you will want to change something or provide some functionality that you cannot implement. If you learn the basics of web development, you will know how to go about resolving these issues.

So, without further ado - let’s meet Github Pages! 

First thing that we are going to have to do is download and install <a href="https://git-scm.com/downloads" target="_blank">Git</a>. Git is a version control system. We will be using it to serve files to our Github Repository - the place where we will store the files for our site.

Now that we have downloaded and installed git, let’s make sure that it works. Open your terminal or command prompt and type the following:

~~~
git --version
~~~

This should output the installed version of git

We are going to have to create an account on Github as well. Go to <a href="https://github.com" target="_blank">Github.com</a> and create a new account (or log in if you already have one).

![github](/assets/images/FirstGithubPage/github.png "github.masterofnone")

Once you have finished creating an account, you are going to want to login and create a new repository. I am going to name my repository ‘firstwebpage.’ You can name yours whatever you would like. Just remember that you cannot use spaces or special characters. 

![github repo](/assets/images/FirstGithubPage/FirstPageRepo.png "github.masterofnone")

Make sure that ‘Initialize this repository with a README’ is unchecked. Click on ‘Create Repository.’ *Important - leave this page open for now. We are going to copy commands from this page later on to push files to this repository. Access other pages from another tab.

Now, let’s create a workspace on our computer. Create a new folder on your Desktop to hold the files for your webpage. I am going to name mine ‘MyFirstWebPage.’ Now, we want to navagate to this folder in our terminal or command prompt. 

~~~
cd Desktop
cd MyFirstWebPage
~~~

We have to get Git to recognize this folder as a local repository. We do that using the ‘init’ command

~~~
git init
~~~

Okay. we have a local repository on our computer and a remote repository on Github. We now have to create content and link the two repositories. The static web page will just be a file named ‘index.html.’ This is the file that your web browser will look to render when directed to your Github Pages site, so make sure you name it index.html. Let’s create a simple index file. 

Open your favorite text editor. I use the free version of <a href="https://www.sublimetext.com/" target="_blank">sublime text</a>, but any text editor will work. Just create a blank file called index.html and save it in the folder that you had created on your Desktop. 

Now, let’s go to <a href="https://getbootstrap.com" target="_blank">getbootstrap.com</a>. Bootstrap is an extremely popular and extremely user-friendly front-end framework for building websites. 

![Bootstrap](/assets/images/FirstGithubPage/BootstrapStarterTemplate.png "Bootstrap")

Scroll down to the Starter template. Copy the code and paste it into your index.html file. Save the file.

![Bootstrap Template](/assets/images/FirstGithubPage/index.png "Bootstrap Template")

If you open the file with your web browser it should look like this:

![Hello World!](/assets/images/FirstGithubPage/helloworld.png "Hello, World")

We have to add this file to git. In the terminal, type

~~~
git add .
~~~

With Git, we have to commit changes before they are seen globally. We do this using the commit -m command. The -m flag lets you commit with a message. You will always want to include this flag and give a short message in quotes to note changes in each commit.

~~~
git commit -m “initial commit”
~~~

Now - we are going to push the file from our local repository to our remote repository from the command line. Remember the Github page that I told you not to close?? Let’s go back to that page. Copy the two commands below ‘push an existing repository from the command line.’ If you did close this page, even though I told you not to, see the info at the end of this article.

![Git Push](/assets/images/FirstGithubPage/push.png "Git Push")

Okay, let’s go back to our terminal or command prompt. Make sure that you are still in the repository that we created on our Desktop. Paste the commands into the terminal

![Git Push Terminal](/assets/images/FirstGithubPage/pushterm.png "Git Push Terminal")

You will be prompted for your username and password for your Github account.
Go to your Github page. Click on the repository name. You should now see your index.html file listed in this repository. You have successfully pushed the index file from your computer to Github. Now, we have to let Github know that you want to serve this file as a webpage.

Go to the Branch tab. Add a new branch named ‘gh-pages’ Make sure that you call it this. This is how you will let Github know where to find the files for this webpage. Save the branch.

![Git Branch](/assets/images/FirstGithubPage/branch.png "Git Branch")

Type the following address into your web browser:

~~~
https://<username>.github.io/<repositoryname>
~~~

Replace <username> with your Github username and <repositoryname> with the name of your Github repository.
Mine looks like this :
https://TheMasterOfNone.github.io/firstwebpage

![First Web Page](/assets/images/FirstGithubPage/helloworld.png "First Web Page")

Congrats! You’ve gone live. If this is your first time working with Git or Github, this probably seems like a lot. It really isn’t. You only have to know a few commands with Git to be proficient, and you use them all the time. If you stick with Github Pages, you will be able to do this in your sleep.

Don’t be discouraged if nothing shows up. Wait a while and try again later. Changes aren’t immediately reflected.

In the next tutorial, we will create a landing page that you can be proud of.

-- As promised, if you had closed the Github page before copying the commands to push your repository, follow these steps
 - Go to your repository on github.com
- Click the ‘clone or download’ button
- Click on the clipboard button to copy the HTTPS address
- In your terminal or command prompt, type
		Git remote add origin 
- Paste the HTTPS address that you had copied to your clipboard at the end of this line
- Hit Enter
- Type the following command into your terminal/command prompt
~~~
		Git push -u origin master
~~~
- Hit Enter
Congratulations, you are back on track.
