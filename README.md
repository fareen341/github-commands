[<h2>1.1 Introduction</h2>](#one)

[<h2>1.2 Configure git bash</h2>](#two)

[<h2>1.3 Starting a project</h2>](#three)

[<h2>1.4 Remote</h2>](#four)

<li>Push</li>
<li>Pull</li>

[<h2>1.5 Making branches</h2>](#five)

<li>Push branch on repo</li>
<li>Merge branch</li>

[<h2>1.6 Add and Commit</h2>](#six)

[<h2>1.7 Status</h2>](#seven) 

<li>Get short summary of all files</li>

[<h2>1.8 To get the last version(Undo changes)</h2>](#eight)

[<h2>1.9 Commit History</h2>](#nine)

[<h2>1.10 Git Diff</h2>](#ten)

[<h2>1.11 Ignoring files</h2>](#eleven)

[<h2>1.12 Deleting(Removing) files</h2>](#twelve)

[<h2>1.13 Fork</h2>](#thirteen)

[<h2>GitHub for DevOps</h2>](#fourteen)

[<h2>Commands related to pust and merge</h2>](#fifteen)

<hr>
<a name="one"><h2>1.1 Course Description</h2></a><br>
<b>Git and Github difference?</b><br>
Git is a version control system that lets you manage and keep track of your source code history. GitHub is a cloud-based hosting service that lets you manage Git repositories. If you have open-source projects that use Git, then GitHub is designed to help you better manage them.<br>

![lifecycle](https://user-images.githubusercontent.com/59610617/130308431-f42b26b6-b70d-40f5-8214-006cd8f67197.png)<br>

The file we make first comes to Untracked area -> move them to staged area -> commit

<b>GIVING READ AND WRITE PERMISSION</b>
<pre>$ git remote add origin (paste the repo url)</pre>
profile->setting->SSH & GPG keys->Generating a new ssh key
<pre>$ ssh-keygen -t ed25519 -C "fareenansari1121@gmail.com"</pre>
<pre>$ eval `ssh-agent -s`</pre>
<pre>$ ssh-add ~/.ssh/id_ed25519</pre>
Adding a new ssh key to your github account
<pre>$ cat ~/.ssh/id_ed25519.pub  -> copy the content and paste it on the new SSH key and give the title ->ok</pre>

Add the remote url
copy the ssh of new repository and paste here
<pre>$ git remote set-url origin git@github.com:gituserfareen/python.git</pre>

<a name="two"><h2>1.2 Configure git bash</h2></a><br>
Create folder-> right click-> open git bash here
Get and set configuration variables that control all facets of how Git looks and operates.<br>
Set the name:
<pre>$ git config --global user.name "User name"</pre>
Set the email:
<pre>$ git config --global user.email "fareenansari33@gmail.com"</pre>
Check the setting:
<pre>$ git config -list</pre>

<b>TO LIST ALL THE FOLDER INCLUDING THE HIDDEN FOLDER</b>
$ ls -lart
$ls  (to display all the folders)

<a name="two"><h2>1.3 Starting a projec</h2></a><br>
There are two ways to start a project.<br>
1)Git init:
<pre>$ git init</pre>
This will Initialized empty Git repository in the current folder. Which is .git hidden folder

2)Git clone
Make a local copy of the server repository.
<pre></pre>$ git clone link_name 
Here we will get the link_name from github , On github ->click on download or clone ->copy the link paste it.<br>
To paste it in the root folder we are working use dot at the end.<br>
<pre>$ git clone link_name</pre>
If we do not use . that will make the folder inside current working dir and make folder of same name as repository, for this we have to first get inside that folder using cd.

<a name="four"><h2>1.4 Remote</h2></a><br>
Create a repository on github ->copy the ssh link
<pre>$ git remote add origin (ssh link)</pre>
To see the link to fetch and push
<pre>git remote -v
example:
origin  git@github.com:fareen341/practice.git (fetch)
origin  git@github.com:fareen341/practice.git (push)
</pre>
<b>Git Push</b><br>
Create index.html file add and commit to check the git push<br>
Push data to the server:
<pre>git push origin master</pre>
Now we can see index.html added successfully on github repo.
After all the changes, files added etc now we want to push everything we done to repo the use .
<pre>git push origin master</pre>
OR
<pre>git push -u origin master</pre>
NOTE: if it shows conflict resolve them first.<br>
<b>Git Pull</b><br>
To pull the changes team made on git files , pull them to my local computer
<pre>$ git pull</pre>
It will pull all the changes someone made or new files added etc. And to check which lines added on particular files we can use $ git log -p -1.<br> 
If it has no new commit or files it will show "up-to-date".<br>

<a name="five"><h2>1.5 Making branches</h2></a><br>
To check on which branch we are currently working
<pre>$ git branch</pre>
This command will show all the branches and the green one is the one we are workin. 

Two methods to create branch<br>
Method 1:Make branch and use checkout to move into that branch
<pre>
$ git branch branch_name   (eg: git branch feature1)
$ git checkout branch_name
</pre>
Method 2:Make branch and simultaneously move into that branch
<pre>$ git checkout -b feature1</pre>
NOTE: These branches will not make any changes into master branch, and after successfully merging the child branch to master we can delete this child branch.
To move this branch on repo.<br>
<b>Push branch on repo</b>
<pre>$ git push -u origin branch_name</pre>
To merge this branch with master.
<pre>
<b>Merge this branch</b>
Go to master branch -> run this command:
$ git merge branch_name</pre>

<a name="six"><h2>1.6 Add and commit</h2></a><br>
After making changes the file will come to modified area , we have to move this file to staged area and then commit.<br>
<b>Moving file to staged area:</b><br>
To move all the files to staged area:
<pre>$ git add -A</pre>
To move single file to staged area.
<pre>$ git add filename</pre>
To commit:
<pre>$ git commit -m "message"</pre>
<b>To move file to staged area and commit simultaneously(not recommended).</b><br>
TO ADD & COMMIT MULTIPLE FILES:
<pre>$ git commit -a -m "message"</pre>

<a name="seven"><h2>1.7 Status</h2></a><br>
We shoud always check the status of our files
<pre>$ git status</pre>
<b>Get short summary of all files</b>
<pre>$ git status -s</pre>
red M shows files are unmodified , green shows the file is added in staged area and ready to commit<br>

<a name="eight"><h2>1.8 To get the last version(Undo changes)</h2></a><br>
CHECKOUT : TO GET BACK THE LAST VERSION OF UR FILES(it match with last commit)
First the info.txt has only Hello World 
After modified it has Hel@@@@@lo Wo@@@@@rld. To get the last commit before add and commit use checkout.
<pre>$ git checkout info.txt  (for one file)</pre>
Now the previous version i.e last commit which is Hello World will be back.
<pre>$ git checkout -f        (for multiple files)</pre>
NOTE: $ git checkout branchname and $ git checkout filename both are used for diffrent purpose.


<a name="nine"><h2>1.9 Commit History</h2></a><br>
GIT LOG<br>
For all the history
<pre>$ git log</pre>
To get last 5 commit
<pre>$ git log -p -5    //only show the last 5 commits</pre>
<pre>$ git log -p -5    //show the last 5 commits with no. of lines added(green color)</pre>
To get the second last commit 
<pre>$ git log -p -2</pre>
To to get third last commit
<pre>$ git log -p -3</pre>
Output:<br>
It will show the changes in green line with +<br>

<a name="ten"><h2>1.10 Git Diff</h2></a><br>
Shows the difference between the compiled file and the line we added(it compares working dir with staging area).
My commit has "Hello World!!!", now i added one line after this 'I added '!' at the end' now if i do git diff, it'll show the green color with + sign 'I added '!' at the end' that is added.
<pre>$ git diff</pre>
show lines added in green line with +

![diff](https://user-images.githubusercontent.com/59610617/130312237-dbf3c69d-2867-41a0-a113-826a21ccd994.png)<br>

To compare staging area with last commit
<pre>$ get diff --staged</pre>

<a name="eleven"><h2>1.11 Ignoring files</h2></a><br>
To ignore the files which has name mylogs.log, mycahces.cache error.txt and compile.txt.<br>
Create .gitignore file-> add the files which i do not want in my repo it can be any files even .html or .txt
<pre>$ touch gitignore</pre>
Open .gitignore and add this name of the files mylogs.log, mycahces.cache error.txt and compile.txt<br>
Now on check status it is not showing that file even for commit or anything.<br>
To ignore files which starts with .py
<pre>*.py add this on .gitignore file</pre>
To ignore a folder add this line in .gitignore:
<pre>myfiles/</pre>

<a name="twelve"><h2>1.12 Deleting(Removing) files</h2></a><br>
Using 1)rm and 2)rm --cached<br>
To remove the file from stage area and local computer too.
<pre>$ git rm file_name</pre>
This will ask for commit, so commit and push.
To just remove it from staged area.
<pre>$ git rm --cached file_name</pre>
It will throw the file from staged area to untrack file it says changes to be commited , so now run the commit command(as in myfile.txt deleted)
If the file is in untract area we must have to once commit this file , we cannot remove the file in untract without commiting.<br>

![commit](https://user-images.githubusercontent.com/59610617/130314216-2a4daff0-92e1-4c04-8967-f98a4a28bf7c.png)<br>

It says file about.html is in untract area and staged area so we don't need this file on repo so we'll commit not add, if we want this about.html file back on repo then we'll do add or we just do commit for deleted file. Now this file will wait in untracked area.<br>

We can now delete this file or add. To delete.
<pre>git clean -n</pre>
This command will show which file will get deleted

Now delete the file for real(f) use f.
<pre>git clean -f</pre>
This command will delete the about.html from local system, so back it up if i need this file in my local machine.

<a name="thirteen"><h2>1.13 Fork</h2></a><br>
It is user to clone some other ppl repo, to get the exact version of other's repo: Go to git -> click on fork -> Done.<br>
Now if i do any changes to this repo it won't affect the owner's repo.

<a name="fourteen"><h2>1.14 Pull Request</h2></a><br>
Make changes ->pull new request ->add comment ->wait for them to accept request and merge


<a name="thirteen"><h2>Github For DevOps</h2></a><br>
<pre>
Why source code mgmt(SCM)(VCM)?
To keep tract of all the changes. Which file gets changed etc.

Centrilized VCS
Disadvantage: When primary server goes down every developer sit idle.

Distributed VCS
cloud based ->collaborator
copy of the entire code will be available using clone etc
Advantage: if the primary server goes down developer will have entire code so they dont have to wait. 
No need to maintain server

S/W: Git, GitHub, BitBucket, GitLab

</pre>

<h2>To see inside the particular version of the file</h2>
<pre>
$ git diff
will return the commit id(version_no)

$ git show commit_id(version_no)
will return what are there inside the file
</pre>

<h2>To unstage</h2>
<pre>
$ git restore --staged filename
</pre>

<h3>Creating a table in readme.md</h3>
<pre>
Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3
</pre>


<h2>Git Log</h2>
<pre>
<b>To see one line</b>
$ git log --oneline

<b>To log on a particular date(give past date)</b>
$ git log --since 2022-02-02

<b>Using until(give current date)</b>
$ git log --until 2022-02-03

<b>Give current & past date too</b>
$ git log --since 2022-02-01 --until 2022-02-03

<b>To filter author</b>
$ git log --author "priya"
$ git log --author "priya" --oneline

<b>Since these particular day what that particulat author has done</b>
$ git log --since 2022-02-01 --until 2022-02-02 --author "priya" --oneline

<b>Search passwd pattern</b>
$ git log --grep "passwd"

<b>Find filename</b>
$ git log --grep "hello.java"

<b>last four commit</b>
$ git log -4

<b>Commit based on branch</b>
$ git log branch_name
</pre>

<b>To ignore particular file</b>
<pre>
!hello.py
</pre>

<b>Startswith</b>
<pre>
[aeiou]*.txt
all files tht startwith aeiou
</pre>

<b>To rename file inside git</b>
<pre>
$ git mv oldfile newfile
$ git mv group groups.java
</pre>

<h2>Fixing a issue in the code</h2>
<pre>
1)copy
2)fix
3)test
4)update then original(master)

<b>How to create copy(branch) of the Repo</b>
create branch which'll have all the master files and then do bugfix inside the new branch
and the merge
$ git merge branch_name
</pre>

<b>To rename branchname</b>
<pre>$ git branch -m bug1 issue1</pre>

<b>To delete branch</b>
<pre>
$ git branch -d issue1
</pre>


<h2>Remote repo using token</h2>
<pre>
On AWS machine adding git url using the acccess token:

Settings -> Developer Settings -> personal access token -> Generate new token -> save it somewhere
Add config user & email 
Now when we push the code it'll ask for username(github username(fareen341)) and pswd(which is access token)

Note: remember to create Token(classic) and check repo checkbox, not fine grane token
</pre>

<a name="fifteen"><h2>Commands related to push & merge</h2></a><br>



