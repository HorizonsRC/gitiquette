Getting started with Git
=========================

Installation
^^^^^^^^^^^^

There are many great Git resources available online, and installing Git on your machine should not be a problem. However, depending on your workflow [LINK], you may find a suitable git integration available to you that does not require a native install of Git on your machine. 

.. tabs::
   .. group-tab:: Windows (Native Git Installation)
    The native installation of Git on Windows includes Git bash, etc....
    
    TODO

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

.. tip:: **Git Gud: One Project, One Repo.**
  
  Repos are very versatile, and essentially allow you to upload any type of file or content. However, it is not appropriate or useful to use repos as a general cloud storage solution. Many of us have picked up bad habits, letting our home folders become bloated and disorganized. Git can help you be more organised, but it does not enforce organisation.

  A general rule of thumb is "One project, one repo." In other words, a repo should contain all the necessary code to serve a single purpose, or do a single thing. Some examples include:
  
  * A single script with its dependency information* and documentation.
    
  * An app with all auxiliary files required to run it, and instructions on how to run them.
    
  * A static html page with all the data, logos and images required to render it.
    
  * A sphinx document containing content files and configuration files to be hosted on ReadTheDocs.

  Of course there are always exceptions to this rule. But remember, if you ever find yourself wondering which repo a certain piece of code is in, you may way to rethink the way you organize your code!

.. note:: **My First Repo**

  But wait, how do I obtain such a repo? I don't have any of those! Read on to find out.
  
  If this is your first time using Git, follow along with the notes labelled **My First Repo**. It will take you through the process of creating your repo, making your first changes, and committing them to the origin repo. Don't worry, this will all make sense by the end of this guide.

Git Hosting Services (E.g GitHub)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Installing Git on your local machine allows you to track changes locally. However, to extend your Git functionality for collaboration, cloud storage, and much more, you need an account on a *Git Hosting Service*. These services serve as a "home" for our repos, acting sort of like a homepage for our codebase. When we navigate to a repo page on a Git Hosting Service, it shows us the files in our repo, and displays our README file, which is where we describe what our code does. In order to create your first empty repo, follow the instructions below. If you want to start from an existing repo on a Git Hosting Service, move on to :ref:`Cloning`.

Making a new repo
^^^^^^^^^^^^^^^^^

.. tabs::
  .. group-tab:: GitHub
   
    #. Sign into GitHub using your Horizons login details. 
   
    .. note:: **Limited GitHub Accounts**
   
      At the time of writing, Horizons seems to be somewhat limited on user accounts. If you're reading this I'm assuming you have been assigned a GitHub account. If not, speak to your manager about getting one.
    
    #. Navigate to the Horizons organization page and click the green button labelled ``New``.

    #. **Repo Name**: Give your repo a name. This is also sometimes known as a "slug" for some reason. This name should be short but descriptive. The convention is to use hyphen-separated, lowercase names. E.g: ``hydro-automation-tools`` or ``sample-qr-code-generator``. Take a moment to think about this name, because while renaming a repo is possible, it can be a bit of a pain.

    #. **Description**: A description is technically optional, but I would strongly encouraged you to make one that is extremely clear about the purpose of your repo. You might find that you need a reminder yourself at some point.

    #. **Public vs Private**: This one is a little tricky, and depends mostly on what you are developing. In general, it is very bad practice to have *any* sensitive information (such as passwords, APIkeys, or - *importantly* - private personal information about individuals) in a repo [SEE SECRETS]. Furthermore, it is unlikely that you, as a Horizons employee, will be required to write any proprietary software. Therefore I would generally encourage the use of public repos unless you are specifically instructed otherwise.

    #. **README files**: Do tick the README file option. This will serve as a "homepage" for your repo, and will be one of your first contributions to your repo.

    #. **.gitignore**: .gitignore files specify which files to exclude from your repo. This is a VERY important file. If you know what your primary development language will be, select it from the list. If you skip this step you will have to do it later. This file will ensure that the most common "ghost files" that are often created by the language interpreters, compilers or common IDE's are not tracked by Git, and is important for a clean repo. [LINK]

    #. **License**: This is another important file which tells others what they are legally allowed to do with your code. Have a read about the most common license types. In most cases I recommend the "GNU General Public License v3.0". This license allows free use of your code, but prevents someone else from ever making money from code that you wrote.

    #. Create repository!


.. note:: **My First Repo: 1. Creating a Repo**

   If you're following this along for the first time, and you don't have any concrete ideas for repos yet, you might be considering creating a repo called "test-repo" or something. This is okay! It's a great way to learn without overthinking things too much. However, consider placing this repo on your own profile so that the Horizons page is reserved for operational code. In the steps above, rather than navigating to the Horizons organisation page, simply hit the ``+`` button at the top left, and select ``New Repository``.

   On the "Create a new Repository" page, confirm that the repo is being placed on your profile by ensuring that the field labelled "Owner*" contains your username rather than HorizonsRC.

   This will result in a url for your repo that looks like ``https://github.com/<your-username>/<your-repo-name>`` rather than ``https://github.com/HorizonsRC/<your-repo-name>``.
  
   You can always delete this repo later, or keep it to practice your new Git skills as you learn them!

.. tip:: **Git Gud: Should this be a new repo?**
   As mentioned previously, repos are meant for a single project. However, the open source community is vast and active. Developers are encouraged to search for existing solutions before implementing their own. If you find a solution that ``nearly`` fits your purpose, consider forking it [LINK] and changing it to suit your needs, or perhaps even contributing to the original project. You'll often find abandoned or unfinished projects that serve your purpose. The open source community is powered by collaboration and cooperation. 
   
  This same principle applies within the Horizons developer community. Before making a new repo on the HorizonsRC GitHub organization, make sure that your problem has not been solved or partially addressed by someone else in the company!
  

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

      
