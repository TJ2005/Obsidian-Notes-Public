---
Title: Version Control
Status: 
marker:
  - "[[Version Control]]"
  - "[[github]]"
tags: 
Date: 2025.02.04
Time: 17:07
---
# Version Control
Version Control as the name suggests is a system that records the the files as they change ( and traverse through multiple states of versions ).

### Why Use a version control
During the development stages a user may want to revert back / look behind / retrieve an older state of the files that they are developing. 
Thus to look behind a records of versions of files can be pulled and used to look up.

The benefits one can have by simply having a version control is endless. Such as
- preventing loss of files
- Reverting back to stages where the project was working
- Comparing and Debugging.
##### Example Case : Graphic Designer / web designer
A graphic designer/web designer must keep a state of all the files so that they compare changes and find the problem of the flaw in their design.

## Local Version Control Systems
Many people opt to do this locally by simply creating a local folder where they make a copy of their project with timestamps. Simple process but its prone to errors.
- Cons: 
	- Lose the entire copied directory
	- Overwrite existing files
	- Lose files to file systems
- Pros:
	- Fast
	- 0 Dependency
	- Easy Setup
	- Privacy
	- Reduced Complexity

![Local Version Control | 500](https://git-scm.com/book/en/v2/images/local.png)

## Centralized Version Control System
To collaborate with multiple developers one can simply use a Centralized Version Control System. These have a single central server that contains all the versioned files and multiple users that have access to checkout.
![Github Centralized Version Control System](https://git-scm.com/book/en/v2/images/centralized.png)

## Distributed Version Controls
Here users are the mirrors. They share their entire repository along with version history to the accessees. Thus, if any server dies, and these systems were collaborating via that server, any of the client repositories can be copied back up to the server to restore it. Every clone is really a full backup of all the data.
<p align="center">
![Distributed Version Controls|500](https://git-scm.com/book/en/v2/images/distributed.png)
</p>



# References


###### Information
- date: 2025.02.04
- time: 17:07