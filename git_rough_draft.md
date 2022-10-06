# What is Version Control?

- Version control is a system that records changes to a file or set of filesover time. It allows you to:
  - Revert selected files back to a previous state
  - Revert the entire project back to a previous state
  - Compare changes over time
  - See who last modified something that might be causing a problem
  - See who introduced an issue and when
  - and more.

<br>

## Local Version Control Systems

![local_VCS](imgs/Local_Version_Control_Systems.png)

- At first, many people’s version-control method of choice was to copy files into another directory (perhaps a time-stamped directory, if they’re clever).This approach was very common because of its simplicity, but it was alsoincredibly error prone.
- Also collaboration was INCREDIBLY difficult and was done rarely

<br>

## Centralized Version Control Systems

![central_VCS](imgs/Centralized_Version_Control_Systems.png)

- To deal with the problem of collaboration, Centralized Version Control Systems (CVCSs) were developed. These systems (such as CVS, Subversion, and Perforce) have a single server that contains all the versioned files, and a number of clients that check out files from that central place. For many years, this has been the standard for version control. This setup offers many advantages, especially over local VCSs. For example:

  - Everyone knows to a certain degree what everyone else on the project is doing.
  - Administrators have fine-grained control over who can do what
  - It’s far easier to administer a CVCS than it is to deal with local databases on every client.

- However, this setup also has some serious downsides:
  - The most obvious is the single point of failure that the centralized server represents. If that server goes down for an hour, then during that hour nobody can collaborate at all or save versioned changes to anything they’re working on.
  - If the hard disk the central database is on becomes corrupted, and proper backups haven’t been kept, you lose absolutely everything — the entire history of the project except whatever single snapshots people happen to have on their local machines.

> Note: Local VCSs suffer from this same problem — whenever you have the entire history of the project in a single place, you risk losing everything.

<br>

## Distributed Version Control Systems

![distributed_VCS](imgs/Distributed_Version_Control_Systems.png)

- This is where Distributed Version Control Systems (DVCSs) step in. In a DVCS (such as Git, Mercurial, Bazaar or Darcs), clients don’t just check out the latest snapshot of the files; rather, they fully mirror the repository, including its full history. Thus, if any server dies, and these systems were collaborating via that server, any of the client repositories can be copied back up to the server to restore it. Every clone is really a full backup of all the data.

- Furthermore, many of these systems deal pretty well with having several remote repositories they can work with, so you can collaborate with different groups of people in different ways simultaneously within the same project. This allows you to set up several types of workflows that aren’t possible in centralized systems, such as hierarchical models.

## Git

#### A Short History of Git

As with many great things in life, Git began with a bit of creative destruction and fiery controversy.

The Linux kernel is an open source software project of fairly large scope. During the early years of the Linux kernel maintenance (1991–2002), changes to the software were passed around as patches and archived files. In 2002, the Linux kernel project began using a proprietary DVCS called BitKeeper.

In 2005, the relationship between the community that developed the Linux kernel and the commercial company that developed BitKeeper broke down, and the tool’s free-of-charge status was revoked. This prompted the Linux development community (and in particular Linus Torvalds, the creator of Linux) to develop their own tool based on some of the lessons they learned while using BitKeeper. Some of the goals of the new system were as follows:

- Speed
- Simple design
- Strong support for non-linear development (thousands of parallel branches)
- Fully distributed
- Able to handle large projects like the Linux kernel efficiently (speed and data size)

Since its birth in 2005, Git has evolved and matured to be easy to use and yet retain these initial qualities. It’s amazingly fast, it’s very efficient with large projects, and it has an incredible branching system for non-linear development.

#### Snapshots, Not Differences

The major difference between Git and any other VCS (Subversion and friends included) is the way Git thinks about its data. Conceptually, most other systems store information as a list of file-based changes. These other systems (CVS, Subversion, Perforce, Bazaar, and so on) think of the information they store as a set of files and the changes made to each file over time (this is commonly described as delta-based version control).

![delta_based_VCS](imgs/Delta_Based_Version_Control.png)

<br>

Git doesn’t think of or store its data this way. Instead, Git thinks of its data more like a series of **snapshots** of a miniature filesystem. With Git, every time you commit, or save the state of your project, Git basically takes a picture of what all your files look like at that moment and stores a reference to that snapshot. To be efficient, if files have not changed, Git doesn’t store the file again, just a link to the previous identical file it has already stored. Git thinks about its data more like a stream of **snapshots**.

![snapshots_based_VCS](imgs/Snapshot_Based_Version_Control.png)

<br>

## Getting Started

After installing Git on your computer you are now ready to begin using this incredible Distributed Version Control Syestem to track the changes in your code. In order to begin tracking the changes and beginning the **Git Workflow** you must first initialize your directory(folder) as a git repository (abbreviated as repo).
Once you have initialized your project's directory, you are ready to continue with **The Three States**.

> Demo how to initialize a Git Repo

## The Three States

Git has three main states that your files can reside in: **modified**, **staged**, and **committed**:

![git_workflow](imgs/Git_Workflow.png)

- Modified means that you have changed the file but have not committed it to your database yet.

- Staged means that you have marked a modified file in its current version to go into your next commit snapshot.

- Committed means that the data is safely stored in your local database.

> Demo how to go thru the basic Git Workflow

## Pushing your Local Repo to a remote repository (Github)

Once you have finished with the Git Workflow and have made your commits, it's time to push it up to Github. GitHub is a code hosting platform for Version Control and collaboration. It lets you and others work together on projects from anywhere.

> Demo how to push up to Github
