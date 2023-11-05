Git Background
=================

What is Git?
------------

Git was written in a fit of pure rage by an angry scandanavian man in 2005. And sometimes it shows. Git has a reputation for being obtuse, cryptic, mysterious and complicated. A lot of this is down to the design of the command-line interface (CLI), which gets a lot of hate. However, in recent years the people behind Git have been actively working towards making this tool more accessible.

If the previous paragraph left you confused or disheartened, don't be! Git is powerful software, and once you get the hang of the basics, you'll find that it can greatly enhance your experience. Git's difficulty curve looks something like this::



                                        |
                                        |
                                        | < Here be dragons
                                        |
                            ____________/ < rebasing??
                           /
                          /
                         / < blaming, tagging...
                        / < restoring, resetting, conflicts...
                       / < cherry-picking, stashing, diffs...
    __________________/ < cloning, add, commit, push, pull, merging, branching, etc.
   /                               (i.e 90% of what you need to know.)
  |
  |

This guide will take you safely up to the first plateau, where you can live happily for a long time. Forever, if you want.

Git is like a digital time machine for your work. It helps you keep track of changes you make to your files, making it easy to go back in time if something goes wrong. Think of it as your safety net, ensuring that your important work is always protected. Git is especially useful when you're working with others on the same project, as it allows everyone to collaborate seamlessly and without fear of messing things up. So, whether you're working on a collaborative project, coding a script for your own use, or even writing up a big report, Git is your trusty tool for keeping everything organized and safe.

  **Nic Notes: Git is only as complicated as what you're trying to do.**
  For example: If dozens of people are trying to make changes to the same codebase at the same time, things are going to get weird. Getting out of a three-way merge conflict (don't worry, this is rare) is going to be an ordeal, no matter what. Git provides a way out by keeping track of which programmer wrote which line of code at what time. While the Git commands necessary to get out of this situation may be complex and require a great amount of experience with Git, there is a pathway to solving this problem without losing code.
  On the other hand, following proper git protocol does prevent such issues from cropping up! If a couple of programmers are working together on a codebase, git provides a collaboration framework that *prevents* merge conflicts for the most part, as well as making them easier to resolve when they do occur!

When is Git Better Than...
--------------------------

**1. Manually Saving Copies onto External/Network Drives or Backup Folders?**
   - **Granular Version Control:** Git excels at tracking changes down to the smallest detail, providing a comprehensive history of your project's evolution. Manually saving copies doesn't offer this level of granularity.  
   - **Efficient Storage:** Git uses space-efficient storage by saving only the differences between versions, while manual backups require storage for each copy of a file, consuming more space.
   - **Streamlined Collaboration:** Git is designed for collaboration, allowing multiple people to work on the same project concurrently without conflicts. Manual backups don't provide this collaboration functionality.
   - **Branching and Merging:** Git enables branching and merging, facilitating different lines of development, a crucial feature for software development. Manual backups don't offer this capability.
     
**2. Cloud-Based Sync Drives such as Google Drive, Dropbox, OneDrive?**
   - **Fine-Grained Version Control:** Git tracks changes in code and text files meticulously, while cloud sync drives are primarily file-sharing tools that lack the same level of detail.
   - **Efficiency and Local Operation:** Git operates locally, allowing you to work offline, and it conserves storage space. Cloud sync drives depend on the internet, may consume more space, and require an online connection for synchronization. (See Git vs Github)
   - **Code Collaboration:** Git is designed for collaborative coding, handling multiple contributors, and merging their changes with ease, while making it easy to resolve any conflicts that may come up. Cloud sync drives may not offer the same level of collaboration support. (See Open Source Software)
   - **Branching and Forking:** Git supports branching and forking of repositories, crucial for open-source and collaborative projects, while cloud sync drives lack similar features. (See Branching, Forking)
     
**3. Automatic Backup Services?**
   - **Version Control for Text-Based Files:** Git is specialized for tracking changes in code, text, and other textual content. Automatic backups will enable you to recover files to a certain time, but will not have a granular log of all changes made or lost. 
   - **Collaboration:** Git is designed for collaboration and code sharing. Automatic backup services are primarily concerned with data recovery and may not facilitate collaboration as effectively.
   - **Efficiency and Storage Optimization:** Git optimizes storage by saving only the differences between versions, reducing space consumption. Automatic backup services store full snapshots of the system, requiring more storage space.By considering these points, you can determine when Git is the superior choice over manual backups, cloud-based sync drives, or automatic OS backup services, especially in the context of version control and collaborative coding.

When is Git NOT the right choice?
---------------------------------

As most powerful productivity tools, Git is fairly specialized. As such, it is not always the most appropriate tool for the job. Git might not be right for...

**1. Non-Textual Content:**
  - Git is primarily designed for tracking changes in text-based files. It may not be the best choice for version control if you're dealing with non-textual content, such as large binary files (e.g., images, videos, or complex proprietary file formats). In such cases, specialized version control systems designed for binary files might be more suitable.

**2. Personal or Simple Projects:**
  - For personal projects or simple tasks that don't involve collaboration or complex version control needs, Git's extensive features might be overkill. In such cases, using Git may add unnecessary complexity to your workflow. Small, single-file scripts or short to-do lists and other notes might be better off tracked in a different way. However, Github does provide a feature known as gists for this purpose!

  **Nic Notes: This does not mean you should not use git for solo development!**
  The framework that Git provides allows and encourages you to be more organized, work more methodically, keep track of your code, and ultimately lose less code. I recommend Git for any solo project that is larger than a single file. Using Git as a solo developer is dead simple, and a great (and stress free) way to get to know it! Git is a muscle. The more you Git, the faster you Git gud.

**3. Real-Time Data Synchronization:**
  - If your primary goal is real-time data synchronization across multiple devices and immediate access to your latest files, cloud-based sync services like Google Drive, Dropbox, or OneDrive might be a more convenient choice. Git operates offline, and synchronization requires explicit actions.

**5. Extremely Large Repositories:**
  - While Git is efficient for versioning, managing extremely large repositories can sometimes be challenging. It may lead to performance issues and increased storage requirements. For such situations, other version control systems or alternative storage methods may be more suitable.

**6. Complexity Aversion:**
  - Git has a learning curve and can be perceived as complex, particularly for individuals who prefer a simple and straightforward approach to version control. If the benefits of Git do not outweigh the effort required to learn it, then a simpler version control system or manual backups might be a more practical choice.

Understanding these situations will help you decide when Git may not be the most appropriate solution, and when alternative methods or tools are better suited to your specific needs.

Git vs Github: Understanding the differences
--------------------------------------------

People unfamiliar with the technology will often use the terms Git and Github interchangeably. This is an understadable mistake, since Git and GitHub are closely related tools, but they serve distinct purposes in the world of version control and collaborative development. Here's a breakdown of their key differences:

**Git:**
  - Version Control System: Git is a distributed version control system (DVCS) designed to track changes in files and directories.
  - Local Operation: Git operates locally on your computer, allowing you to track changes, create commits, and manage versions without the need for an internet connection.
  - Command-Line and GUI: Git is primarily used through command-line interfaces, but there are also graphical user interfaces (GUIs) available.
  - Independent of Hosting Platforms: Git is not tied to any specific hosting platform and can be used with various repository hosting solutions or even as a stand-alone tool.
  - Private or Self-Hosted Repositories: You can create private Git repositories, and self-hosted Git servers provide control over your code's security and access.

**GitHub:**
  - Hosting Platform: GitHub is a web-based platform that provides hosting and collaboration tools for Git repositories. It's a central hub for storing, sharing, and collaborating on Git-based projects.
  - Online Repository Hosting: GitHub stores your Git repositories in the cloud, allowing you to access them from anywhere with an internet connection.
  - Collaboration and Social Features: GitHub offers collaboration features like pull requests, issues, wikis, and project boards. It also fosters a social aspect where developers can follow projects, contribute, and showcase their work.
  - Web Interface: GitHub provides a user-friendly web interface for interacting with Git repositories, making it accessible to a wide range of users, even without in-depth Git knowledge.
  - Public and Private Repositories: GitHub supports both public and private repositories. Public repositories are openly accessible, while private repositories are secure and require permission to access. 
  - In summary, Git is the version control system that manages changes locally on your computer and is not tied to any specific platform. GitHub, on the other hand, is a web-based hosting platform that extends Git's functionality by providing a central hub for collaboration, remote access, and social interaction. Understanding the differences between these two tools will help you decide how to best leverage their capabilities in your development projects.

**Git and GitHub: A match made in heaven!**
""""""""""""""""""""""""""""""""""""""""""""""

Without GitHub, Git is a powerful but limited tool that tracks local file changes on your computer. Without Git, GitHub is a cloud-based storage solution for your code. When used together, GitHub extends the already powerful capabilities of Git to the cloud, allowing us to distribute, share, collaborate, track changes, log issues, host documentation, automate processes, and much more. 

**Git and GitHub: Not the only options!**
""""""""""""""""""""""""""""""""""""""""""""

With some exceptions, most of what has been said thusfar applies not only to Git and GitHub, but to distributed version control systems in general. Both technologies have numerous alternatives available. Alternatives for Git include Mercurial SCM and Apache Subversion. Alternatives for GitHub include GitLab or BitBucket. All of these technologies have their merit, but the combination of Git and GitHub is by far the most popular. This means that documentation and online support is more readily available, and the tech itself is mature and stable. For these reasons, Horizons staff are encouraged to use Git and GitHub to ensure that the collaboration features are fully utilised. 
