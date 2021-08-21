[<h2>1.1 Introduction</h2>](#one)

[<h2>1.2 Configure git bash</h2>](#two)

[<h2>1.3 Starting a project</h2>](#three)

[<h2>1.4 Remote</h2>](#four)

[<h2>1.5 Making branches</h2>](#five)






[<h2>1.4 Track changes</h2>](#two)

[<h2>1.5 Commit history</h2>](#two)

[<h2>1.6 Track changes</h2>](#two)

[<h2>1.7 Track changes</h2>](#two)

[<h2>1.8 Ignoring files</h2>](#two)

[<h2>1.9 Branching</h2>](#two)

[<h2>1.10 Merging</h2>](#two)

[<h2>1.11 Remote</h2>](#two)

[<h2>1.12 Push Updates</h2>](#two)

[<h2>1.13 Pull Updates</h2>](#two)

[<h2>1.14 Undo Changes</h2>](#two)

[<h2>1.15 Removing Files</h2>](#two)

hr
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
<pre>$ git config --global user.email "himanshudubey481@gmail.com"</pre>
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
Create index.html file add and commit to check the git push<br>
Push data to the server:
<pre>git push origin master</pre>
Now we can see index.html added successfully on github repo.

<a name="four"><h2>1.5 Making branches</h2></a><br>
To check on which branch we are currently working
<pre>$ git branch</pre>
This command will show all the branches and the green one is the one we are workin. 

Two methods to create branch<br>
Method 1:Make branch and use checkout to move into that branch
<pre>
$ git branch branch_name   (eg: git branch feature1)
$ git checkout branch_name
</pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>
<pre></pre>

