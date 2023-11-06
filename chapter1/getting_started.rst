Getting started with Git
=========================

Important Git Concepts
------------------------

Repository/repo
^^^^^^^^^^^^^^^^
A git repository ("repo" for short) is a folder within which every change is tracked using git. Git keeps track of every line of code/text in every file in that folder, and records how they change. 

Git knows that a directory is a repo by looking for a folder called ``.git/``. Because this folder begins with a ``.``, many file explorers choose to hide it from view as a "dotfile".

When in doubt, it is easy to find out whether your folder is a repo or not:

.. tabs::
   .. group-tab:: Git CLI
      
      The ``git status`` command is a very useful tool for many applications. I rely heavily on this command to provide me with an overview of what's going on in my repo. When running this (or any) command outside of a git repo, you will be met with something like this:
   
      .. code::
         
        $ git status
        fatal: not a git repository (or any of the parent directories): .git
        
        This indicates that Git could not find the ``.git`` folder in this directory, or in any parent directory, meaning that this is not set up as a git repository. 
      
      Otherwise, when run in a git repo, you'll be met with:

      .. code::
         
        $ git status
        On branch main
        Your branch is up to date with 'origin/main'.

        nothing to commit, working tree clean

      Great! Git was able to see your ``.git`` folder, recognise the git repo, and give you some information about the current state of your repo. Don't worry about the output for now, you'll understand it before long!

.. tip:: Git Gud: One Project, One Repo.
  
  Repos are very versatile, and essentially allow you to upload any type of file or content. However, it is not appropriate or useful to use repos as a general cloud storage solution. Many of us have picked up bad habits, letting our home folders become bloated and disorganized. Git can help you be more organised, but it does not enforce organisation.

  A general rule of thumb is "One project, one repo." In other words, a repo should contain all the necessary code to serve a single purpose, or do a single thing. Some examples include:
  - A single script with its dependency information* and documentation.
  - An app with all auxiliary files required to run it, and instructions on how to run them.
  - A static html page with all the data, logos and images required to render it.
  - A sphinx document containing content files and configuration files to be hosted on ReadTheDocs.

  Of course there are always exceptions to this rule. But remember, if you ever find yourself wondering which repo a certain piece of code is in, you may way to rethink the way you organize your code!

But wait, how do I obtain such a repo? I don't have any of those! Read on to find out.

Git Hosting Services (E.g GitHub)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Installing Git on your local machine allows you to track changes locally. However, to extend your Git functionality for collaboration, cloud storage, and much more, you need an account on a *Git Hosting Service*. These services serve as a "home" for our repos, acting sort of like a homepage for our codebase. When we navigate to a repo page on a Git Hosting Service, it shows us the files in our repo, and displays our README file, which is where we describe what our code does. In order to create your first empty repo, follow the instructions below. If you want to start from an existing repo on a Git Hosting Service, move on to :ref:`Cloning`.

Cloning
^^^^^^^^^
Most of the time, the way you'll get a repo on to your computer is by ``cloning`` it from the internet to your local computer. Cloning is the process of making a copy of the codebase, along with all the git information. Cloning is simple.
To start we need to get the url of our Git repo, i.e. the address of it's location on our Git hosting service.

.. tabs::
  .. group-tab:: GitHub
      In github, you can find the repo url by clicking the green drop-down button labelled ``<> Code`` in the top right. Copy the text in the text field under the HTTPS tab. It should look something like ``https://github.com/<user_or_org_name>/<repo_name>.git``

  If you don't have a GitHub repo and want to make one from scratch, see [The section about that].

.. tabs::
  .. group-tab:: Git CLI
      
      Cloning is easy! Start by navigating to the folder where you want to store your code. I usually put a folder in my home directory called ``repos``.

      .. code::
        
        .../$ cd repos
        .../repos$ ls
        <no output means no repos yet!>
      
      Now we can clone our repo:

      .. code::

        .../repos$ git clone https://github.com/<user_or_org_name>/<repo_name>.git

        No output is good news! Let's confirm that this worked by looking at our new repo:
      
      .../repos$ ls
      <repo_name> 

      There it is. Looking inside that folder we should be able to see any and all code created so far.
      
      .. code::
         
        .../repos/$ cd <repo_name>
        .../repos/<repo_name>$ ls
        python_script.py README.md
        .../repos/<repo_name>$ git status
        On branch main
        Your branch is up to date with 'origin/main'.

      nothing to commit, working tree clean

      On 
