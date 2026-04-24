# Challenge #1
***Name:*** Version Control
* An employee's computer was compromised and we saw this backup file leave the network
* Need to find out what information the hacker got
* This challenge will involve using [git version control](https://en.wikipedia.org/wiki/Git)
# Lesson 
1. Download the ***git zip** file
2. ```unzip [filename]``` ~ Used to unzip the file
   * Once this is done, the unzipped version of the file will be available
3. ```cd [filename]``` ~ Change Directory to the file
   * See what is inside with the ```ls``` command
   * The ```ls -a``` command will display all files and directories
   * There is a ```.git``` directory that will allow us to leverage [git](https://docs.github.com/en/get-started/using-git/about-git) and extract information
4. ```git log``` Will allow use to view details like Authpr, Date, and commit
5. Once we have this information, we can copy the commit that we want to investigate the changes that were made in each one
   * ```git show [commit] #Show information about the commit```
   * After inspecting the remaining commits, I see that the flag was erased in a later version
6. ```git branch #Find other availabe branches```
7. ```git checkout [branch] #Switch over to the "branch"```
