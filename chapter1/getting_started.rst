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
 


add
^^^^^^^^^^^^^

When you make changes to a 
