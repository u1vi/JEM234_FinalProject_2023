# JEM234_FinalProject_2023

Git gc and Git prune 

Git gc 

According to documentation (Linux terminal) 

```bash
$ git help gc
git-gc - Cleanup unnecessary files and optimize the local repository 
``` 

The "git gc" command is like a cleanup tool for your Git repository. It's called "garbage collection" because it helps Git tidy up and get rid of unnecessary stuff that piles up. This concept originally comes from how some computer programs manage memory. 

But what the garbage means

media/MegasXLR_searching_item.mp4

https://user-images.githubusercontent.com/6877923/115474571-03c75800-a23e-11eb-8096-8973aad5fa9f.mp4


In your Git repository, there are things we call "garbage." One type of this garbage is like forgotten, hidden treasures. These are the commits that become hidden when you do things like changing the history with "git reset" or "git rebase." Git doesn't throw them away to be safe and not lose important stuff. You can still see these hidden commits and use them if needed. 

So, when you run "git gc," you're basically telling Git to clean up this mess, like finding and organizing those hidden treasures so that your Git history stays neat and organized. 

Think of your Git repository like a library of books. In this library, each book represents a file or some piece of data. Now, we have two kinds of books: "reachable" and "unreachable." 

Reachable Books: Imagine you want to find a specific book in the library. You can easily find it if there's a clear path of signs or tags that lead you to that book. These signs are like branches or tags in Git. So, if you can follow these signs, you're dealing with reachable books. 

Unreachable Books: Now, picture a book hidden away on a dusty shelf with no signs or labels pointing to it. Nobody knows it's there, and it's hard to find. These books are unreachable because there are no signs (branches or tags) guiding you to them. 

In Git, "reachable" objects are like the books you can easily find because there are clear paths (branches or tags) leading to them. "Unreachable" objects are like the hidden books on dusty shelves – no signs or labels (branches or tags) point to them, making them difficult to access. 

So, Git's job is to keep the library organized, making sure that reachable books are easy to find while also cleaning up and getting rid of those dusty, unreachable books to save space and keep things tidy. This way, your Git repository remains efficient and clutter-free. 

 

