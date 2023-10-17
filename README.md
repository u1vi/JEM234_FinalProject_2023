# JEM234_FinalProject_2023

## Git gc and Git prune 

### Git gc 

According to documentation (Linux terminal) 

```bash
$ git help gc
git-gc - Cleanup unnecessary files and optimize the local repository 

``` 


The "git gc" command is like a cleanup tool for your Git repository. gc means "garbage collection" because it helps Git tidy up and get rid of unnecessary stuff that piles up. This concept originally comes from how some computer programs manage memory. 

### Git prune 

According to documentation (Linux terminal) 

```bash
$ git help prune
git-prune - Prune all unreachable objects from the object database

``` 
The "git prune" is a command for cleaning up your project. It deletes things you no longer need, like old files. When your project doesn't use something anymore, git prune removes it. In simple terms, it helps you keep your project clean and easy to work on.

## But what the garbage or unreachable files means

https://github.com/u1vi/JEM234_FinalProject_2023/assets/68427789/97ed9c9e-cb19-4670-abc4-875eea470208

In the context of programming languages, such as Java, "garbage" refers to memory that was previously allocated for objects but is no longer needed or accessible by the program. This unused memory may accumulate over the course of program execution. Garbage collection is the process through which the programming language's runtime environment (in Java's case, the JVM) identifies and removes these unused objects, freeing up memory for other purposes. This helps ensure efficient memory management and prevents memory leaks, where resources are occupied by objects that are no longer in use.

In your Git repository, there are things we call "garbage." One type of this garbage is like forgotten, hidden treasures. These are the commits that become hidden when you do things like changing the history with "git reset" or "git rebase." Git doesn't throw them away to be safe and not lose important stuff. You can still see these hidden commits and use them if needed. 

So, when you run "git gc," you're basically telling Git to clean up this mess, like finding and organizing those hidden treasures so that your Git history stays neat and organized. 

Think of your Git repository like a library of books. In this library, each book represents a file or some piece of data. Now, we have two kinds of books: "reachable" and "unreachable." 

Reachable Books: Imagine you want to find a specific book in the library. You can easily find it if there's a clear path of signs or tags that lead you to that book. These signs are like branches or tags in Git. So, if you can follow these signs, you're dealing with reachable books. 

Unreachable Books: Now, picture a book hidden away on a dusty shelf with no signs or labels pointing to it. Nobody knows it's there, and it's hard to find. These books are unreachable because there are no signs (branches or tags) guiding you to them. 

In Git, "reachable" objects are like the books you can easily find because there are clear paths (branches or tags) leading to them. "Unreachable" objects are like the hidden books on dusty shelves – no signs or labels (branches or tags) point to them, making them difficult to access. 

So, Git's job is to keep the library organized, making sure that reachable books are easy to find while also cleaning up and getting rid of those dusty, unreachable books to save space and keep things tidy. This way, your Git repository remains efficient and clutter-free. 

### If you are saying: 
  *Okay now I have some notion, but what is the difference between them if both delete unnecessary files?*

### Congratulations  we are on the same side.

If we look at the documentation of the git prune closely, there is one interesting note under the *DESCRIPTION* subpart.


   ```bash
$ git help prune
    Note
    In most cases, users should run git gc, which call git prune.

``` 
According to **[atlassian](https://www.atlassian.com/git/tutorials/git-gc#:~:text=git%20gc%20vs%20git%20prune,by%20the%20git%20gc%20configuration.)**. <br>
**git gc** is a parent command and **git prune** is a child. git gc will internally trigger git prune. git prune is used to remove Git objects that have been **deemed** inaccessible by the git gc configuration. Learn more about git prune.

### Analogy time
![emperior](https://github.com/u1vi/JEM234_FinalProject_2023/assets/68427789/4beb3121-e9ae-48cf-979a-920bf2766139)


**Git GC as the Emperor:** Think of git gc as the wise emperor of your Git repository. It oversees all matters, including the cleanliness and optimization of your kingdom (repository). Just like an emperor decides the fate of the prisoner, git gc decides the fate of your Git files.

**Git Prune as the Executioner:** Now, consider git prune as the executioner in your kingdom. When there's a file that's no longer needed, it's like a prisoner waiting for judgment. git prune plays the role of the executioner, deciding whether to delete the file (carry out the execution) or spare it. It's the one who executes the decision made by the emperor (git gc) about the file's fate.
