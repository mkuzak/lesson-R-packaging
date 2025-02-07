---
title: "Getting started"
teaching: 15
exercises: 10
questions:
- "I want to write a package. Where should I start?"
objectives:
- "Create a minimal package"
keypoints:
- "A package is no more and no less than a folder structure"
- "RStudio can help you"
---

## What does a package look like?

The minimal folder structure of a package looks like this

~~~sh
.
├── R
│   └── <R functions>
├── README.md
├── LICENSE
├── DESCRIPTION
└── NAMESPACE
~~~
{: .source}

where:

- The folder `R` contains all the `R` code (more on this in [episode 4](../04-functions)).
- The `README.md` file contains human-readable information about the package (more on this in [episode 4](../04-functions)).
- The `LICENSE` contains information about who and how can use this package (more below).
- The `DESCRIPTION` file contains information about the package itself (more information on the [episode 7](../07-dependencies)).
- The `NAMESPACE` file is automatically generated and tells R which functions can be accessed (more on [episode 6](../06-documentation)).

## A minimal package

The menus in `RStudio` will help us in creating the most minimal of packages.
Let's open `RStudio` and look at the upper left corner.
We will press `File > New project > New directory`, and see a menu like this:

![New project menu](../fig/new-project.png)

As you can guess, we'll now press `R package`.
The new menu asks us to fill in some information.
For the moment, bear with me and fill in the following:

![New project menu](../fig/create-package.png)

Notice that:

- We gave the package a name: `mysterycoffee`.
- I created my package on my `~/Desktop` folder, but you can use another location if you prefer.
- We left `Create git repository` unticked. If you want to know more about `git`, please refer to our courses on [Version control](https://swcarpentry.github.io/git-novice/). Integrating packages with Git is very useful, but we will not talk about it in this lesson. 
- We left `Use renv with this project unticked`.
- We ticked `Open in new session`.

Now we are ready to press `Create Project`.

> ## What just happened?
> After pressing `Create Project`, a new `RStudio` window should have appeared.
> The working folder should be `mysterycoffee`, and it should already have some contents:
> 
> ![New project menu](../fig/contents.png)
>
> Also, the file `./R/hello.R` would appear open in the editor.
> This is an example file that contains a toy function.
> Its only functionality is to, well, to say _"hello"_.
> This may sound silly, but it will help you writing your first packaged R functions.
{: .callout}

> ## The `hello.R` file
> Let's take a look at the `hello.R` file.
> You'll see that it contains a tiny function and some comments.
> The comments are actually more important that the function itself.
> They contain very useful tips about how to install, check and test the package.
>
> As a rule of thumb: always read the contents of the example files RStudio creates for you.
{: .callout}

## Play with the package

Believe it or not, this package is ready to be installed.
Just go to the upper right corner and press `Build > Install and Restart`.

![Install and restart](../fig/install-and-restart.gif)

This will install and attach the package.
Now, you can use `hello`, the only function that this package contains so far.
If you try it by using:

~~~r
hello()
~~~
{: .source}

it should print:

~~~r
# Hello, world!
~~~
{: .output}

> ## Tell me how you load your functions
> There are many ways of using functions, but all of them involve loading them into the workspace.
> We just learned how to do that using a package.
>
> **How do you usually work with functions?**
> Perhaps you source them from an external file?
> Do you usually work on a single, long script?
>
> **Can you think of any advantage of using packages instead?**
> Don't worry if the answer is no.
> This is actually a difficult question at this stage.
> We'll show the full power of packages along the course.
{: .discussion}

## More advanced folder structures
In this course we will show you how to unleash the full power of packaging.
In order to do so, we will use some optional folders.
You can see an overview below

~~~sh
.
├── R
│   └── <R functions>
├── data (optional)
│   └── <data>
├── tests (optional)
│   ├── testthat.R
│   └── testthat
│       └── <tests>
├── vignettes (optional)
│   └── <Rmd vignettes>
├── inst (optional)
│   └── <any other files>
├── README.md
├── LICENSE
├── DESCRIPTION
└── NAMESPACE
~~~
{: .source}

where:

- The `data` folder contains, as the name suggests, data (more on [episode 8](../data)).
- The `tests` folder contains unit tests, that will be very useful for making our package robust and mantainable (more on [episode 5](../05-testing)).
- The `vignettes` folder contains documentation in `Rmd` format. As we'll see, this is a very suitable format for your reports and publications (more on [episode 9](../09-vignettes)).
- The `inst` folder contains any extra file you may want to include (more on [episode 8](../data)).

{% include links.md %}
