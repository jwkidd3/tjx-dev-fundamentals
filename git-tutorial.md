
# GIT and DEVOPS Training

## how to create ssh key for github

>
$ ls -al ~/.ssh
# Lists the files in your .ssh directory, if they exist
generate ssh key github

>
$ ssh-keygen -t ed25519-sk -C "your_email@example.com"

### add ssh keys to github
>
    1. ssh-keygen -o -t rsa -C "your_email@example.com"
    2. Press return for each option
    3. cat ~/.ssh/id_rsa.pub               # This is your public key file ends with .pub
    4. Copy the entire cat's output on "Settings - SSH and GPG keys - New SSH key" on GitHub
    5. 




## Ensure you have a Github account created.
### Github Account Creation Steps:
1. Open https://github.com in a web browser, and then select Sign up.
2. Enter your email address.
3. Create a password for your new GitHub account, and Enter a username, too. Next, choose whether you want to receive updates and announcements via email, and then select Continue.
4. Verify your account by solving a puzzle. Select the Start Puzzle button to do so, and then follow the prompts.
5. After you verify your account, select the Create account button.
6. Next, GitHub sends a launch code to your email address. Type that launch code in the Enter code dialog, and then press Enter.
7. GitHub asks you some questions to help tailor your experience. Choose the answers that apply to you in the following dialogs:
8. On the Where teams collaborate and ship screen, you can choose whether you want to use the Free account or the Team account. To choose the Free account, select the Skip personalization button.

## Next Steps

### Create and use a repository

> Open a project from a GitHub repo:

    Visual Studio makes it easy to open a project from a repo. You can do so when you start Visual Studio, or you can do so directly from within the Visual Studio IDE.

    1 Open Visual Studio.
    2 On the start window, select Clone a repository.
    3 Enter or type the repository location, and then select the Clone button.
    4 You might be asked for your user sign-in information in the Git User Information dialog box. You can either add   your information or edit the default information it provides.
    5 Select Save to add the info to your global .gitconfig file. (Or, you can select Cancel if you>d like to add the info later.)
> FOr Visual Steps follow the below link : https://visualstudio.microsoft.com/vs/github/


# SSH Keys for GitHub

### Why Use an SSH Key?
**********************************************************************************************************************************************
>
    When working with a GitHub repository, you'll often need to identify yourself to GitHub using your username and password. An SSH key is an alternate way to identify yourself that doesn't require you to enter you username and password every time.

    SSH keys come in pairs, a public key that gets shared with services like GitHub, and a private key that is stored only on your computer. If the keys match, you're granted access.

    The cryptography behind SSH keys ensures that no one can reverse engineer your private key from the public one.
Generating an SSH key pair

1. The first step in using SSH authorization with GitHub is to generate your own key pair.

2. You might already have an SSH key pair on your machine. You can check to see if one exists by moving to your .ssh directory and listing the contents.

    $ cd ~/.ssh
    $ ls
If you see id_rsa.pub, you already have a key pair and don't need to create a new one.

3. If you don't see id_rsa.pub, use the following command to generate a new key pair. Make sure to replace your@email.com with your own email address.

    >
        $ ssh-keygen -o -t rsa -C "your@email.com"
(The -o option was added in 2014; if this command fails for you, just remove the -o and try again)

 When asked where to save the new key, hit enter to accept the default location.

    Generating public/private rsa key pair.
    
    Enter file in which to save the key (/Users/username/.ssh/id_rsa):
4. You will then be asked to provide an optional passphrase. This can be used to make your key even more secure, but for this lesson you can skip it by hitting enter twice.

Enter passphrase (empty for no passphrase):
Enter same passphrase again:
When the key generation is complete, you should see the following confirmation:

    Your identification has been saved in /Users/username/.ssh/id_rsa.
    Your public key has been saved in /Users/username/.ssh/id_rsa.pub.
 
- The key fingerprint is:

~~~
    01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your@email.com
    The key's randomart image is:
    +--[ RSA 2048]----+
    |                 |
    |                 |
    |        . E +    |
    |       . o = .   |
    |      . S =   o  |
    |       o.O . o   |
    |       o .+ .    |
    |      . o+..     |
    |       .+=o      |
+-----------------+
The random art image is an alternate way to match keys but we won't be needing this.

~~~~
5. Add your public key to GitHub
We now need to tell GitHub about your public key. Display the contents of your new public key file with cat:
~~~~
    $ cat ~/.ssh/id_rsa.pub
~~~~
The output should look something like this:
~~~~
    ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEA879BJGYlPTLIuc9/R5MYiN4yc/YiCLcdBpSdzgK9Dt0Bkfe3rSz5cPm4wmehdE7GkVFXrBJ2YHqPLuM1yx1AUxIebpwlIl9f/aUHOts9eVnVh4NztPy0iSU/Sv0b2ODQQvcy2vYcujlorscl8JjAgfWsO3W4iGEe6QwBpVomcME8IU35v5VbylM9ORQa6wvZMVrPECBvwItTY8cPWH3MGZiK/74eHbSLKA4PY3gM4GHI450Nie16yggEg2aTQfWA1rry9JYWEoHS9pJ1dnLqZU3k/8OWgqJrilwSoC5rGjgp93iu0H8T6+mEHGRQe84Nk1y5lESSWIbn6P636Bl3uQ== your@email.com
~~~~
   
    Copy the contents of the output to your clipboard.
    
6. Go to your github account and add the rsa key that you have generated following steps 1-5. Check the screenshot below .

![](/images/Adding_ssh_keys.PNG)


### *** Some important things to note if you are getting any errors

Make sure you are using ssh for your repository also

    git remote -v
    origin  git@github.com:eMahtab/reponame.git (fetch)
    origin  git@github.com:eMahtab/reponame.git (push)
    
>
Don't use https, if your remote is using https then it will keep asking for password, even If you have added the public key to Github and added private key to ssh-agent. Below will always ask for password



### Make changes to a file and push them to GitHub as commits
 1. cd /your_project path ~~~~

     1. git add *
     2. git commit -m "Enter commit message here"
     3. git push -u origin "YYourBranchName"

### Open and merge a pull request





## Git Branching and Merging

### Create a new branch with git and manage branches

In your Github fork, you need to keep your master branch clean, by clean I mean without any changes, like that you can create at any time a branch from your master. Each time that you want to commit a bug or a feature, you need to create a branch for it, which will be a copy of your master branch.


1.  When you do a pull request on a branch, you can continue to work on another branch and make another pull request on this other branch.
    Before creating a new branch, pull the changes from upstream. Your master needs to be up to date.

$ git pull

2. Create the branch on your local machine and switch in this branch :

 $ git checkout -b [name_of_your_new_branch] 
3. Push the branch on github :

 $ git push origin [name_of_your_new_branch] 
4. When you want to commit something in your branch, be sure to be in your branch. Add -u parameter to set-upstream.

    You can see all the branches created by using :

    > $ git branch -a 

    Which will show :

    * approval_messages
    master
    master_clean
5. Add a new remote for your branch :

    > $ git remote add [name_of_your_remote] [name_of_your_new_branch]
6. Push changes from your commit into your branch :

    > $ git push [name_of_your_new_remote] [url]
    OR 
    > $ git push -u  origin [name_of_your_new_remote]

7. Update your branch when the original branch from official repository has been updated :

    > $ git fetch [name_of_your_remote]

8. Then you need to apply to merge changes if your branch is derivated from develop you need to do :

    > $ git merge [name_of_your_remote]/develop

9. Delete a branch on your local filesystem :
    Ensure you have switched your barnch to main otherwise it may give error.
    > git switch main

    > $ git branch -d [name_of_your_new_branch] 
    Example: git branch -d  git-commands
    Output:  Deleted branch git-commands (was 601b25c).

10. To force the deletion of local branch on your filesystem :

    > $ git branch -D [name_of_your_new_branch]
    Delete the branch on github :

    > $ git push origin :[name_of_your_new_branch]
    The only difference is the: to say delete, you can do it too by using GitHub interface to remove branch: https://help.github.com/articles/deleting-unused-branches.

    If you want to change default branch, it>s so easy with GitHub, in your fork go into Admin and in the drop-down list default branch choose what you want.

    ### If you want create a new branch:

    > $ git branch <name_of_your_new_branch>


## In summary, if you want to contribute to a project, the simplest way is to:

    - Find a project you want to contribute to
    - Fork it
    - Clone it to your local system
    - Make a new branch
    - Make your changes
    - Push it back to your repo
    - Click the Compare & pull request button
    - Click Create pull request to open a new pull request



# We are learning to develop a claculator app

## CalculatorApp-In-Flask

### 💻 Tech Stack
### Front-End:
<img alt="HTML5" src="https://img.shields.io/badge/html5%20-%23E34F26.svg?&style=for-the-badge&logo=html5&logoColor=white"/>  <img alt="CSS3" src="https://img.shields.io/badge/css3%20-%231572B6.svg?&style=for-the-badge&logo=css3&logoColor=white"/> <img alt="JavaScript" src="https://img.shields.io/badge/javascript%20-%23323330.svg?&style=for-the-badge&logo=javascript&logoColor=%23F7DF1E"/> 
<img alt="BootStrap" src="https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white"/> 

### Back-End:
<img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/> <img alt="Flask" src="https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white"/> 

## 🚀 Quick Start :


#### Step 1: Forking the repository :

To work on an open-source project, you will first need to make your copy of the repository. To do this, you should fork the repository and then clone it so that you have a local working copy.

Get your own Fork/Copy of repository by clicking `Fork` button right upper corner.<br><br>

#### Step 2: Clone the Forked Repository

After the repository is forked, you can now clone it so that you have a local working copy of the codebase.

To make your local copy of the repository follow the steps:
- Open the Command Prompt
- Type this command:
  
```bash
$ git clone https://github.com/<your-github-username>/CalculatorApp-In-Flask
```


#### Step 3: Creating a new branch (IMP)
This is one of the very important step that you should follow to contribute in Open Source. A branch helps to manage the workflow, isolate your code and does not creates a mess. To create a new branch:
  
```bash
$ git branch <name_of_branch>
$ git checkout -b <name_of_branch>
```

Keep your cloned repo upto date by pulling from upstream (this will also avoid any merge conflicts while committing new changes)
```bash
git pull origin main
```

#### Step 4: Setting up Project
##### For Flask:

**1. Create a Virtual Environment**

- *On macOS and Linux:*
  ```bash
    python -m venv calculator
  ```
- *Windows*
  ```bash
    py -m venv env
  ````

**2. Activate the Virtual Environment**
  - *On Windows*
    ```bash
    .\env\Scripts\activate
    ```
  - *On macOS and Linux:*
    ```bash
    source calculator/bin/activate
    ```

**3. Install dependencies using**
```bash
pip install -r requirements.txt
```

**4. Run server using**

```bash
python main.py

OR

flask run

```

**5.** Go to ` http://127.0.0.1:5000/` and enjoy the application.

#### Step 5: Contribute
Make relevant changes according to the issue that you were assigned on. Contribute in any way you feel like :)

#### Step 6: Commiting and Pushing
Once you have modified an existing file or added a new file to the project, you can add it to your local repository, which we can do with the git add command.

```bash
git add .
```
With our file staged, we’ll want to record the changes that we made to the repository with the git commit command.

The commit message is an important aspect of your code contribution; it helps the other contributors fully understand the change you have made, why you made it, and how significant it is.

```bash
git commit -m "useful commit message"
```

At this point you can use the git push command to push the changes to the current branch of your forked repository:

```bash
git push origin <branch-name>
```

#### Step 7: Create Pull Request
Now, you are ready to make a pull request to the original repository.

You should navigate to your forked repository, and press the "Compare & pull request" button on the page.

GitHub will alert you that you can merge the two branches because there is no competing code. You should add in a title, a comment, and then press the “Create pull request” button.


<br>
show some ❤️&nbsp; by giving the star to this repo
