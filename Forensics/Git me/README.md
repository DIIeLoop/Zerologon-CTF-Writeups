Git Me Challenge Write-up

Challenge Description:  There are too many brunches of a tree try to find the real flag
 
Challenge Goal:The challenge's main objective is to navigate the Git repository, discover hidden branches and commits, analyze files, and identify the secret flag. The challenge requires familiarity with Git commands and some basic understanding of encryption techniques.

Solution Steps: 
---------------------------------
Step 1: Listing All Branches 

The first task was to explore all branches in the repository. Using the following command: git branch -a  

We discovered several branches in the repository, including:

main
remotes/origin/gitignore
remotes/origin/history
remotes/origin/master

---------------------------
Step 2: Exploring the "history" Branch

To begin the investigation, I switched to the history branch using:
git checkout remotes/origin/history  

I explored the files in this branch and found several text files including:

Hint.txt
Dowhill.txt
shadows_basics.txt 

After opening Hint.txt, the hint was clear: "Try to see the history."
----------------------------------
Step 3: Checking Commit History

Based on the hint, I examined the commit history using:
git log --oneline  

I found three key commits:
.Adding Hint.txt
.Adding Dowhill.txt
.Adding shadows_basics.txt
-----------------------------------
Step 4: Exploring the "gitignore" Branch

Since nothing useful was found in the history branch, I decided to switch to the gitignore branch using:

git checkout remotes/origin/gitignore  

In this branch, I found a hidden file named .flag. When I opened it, I found a fake flag:      zeroday{fakeflag}

-------------------------------------
Step 5: Analyzing Code and Searching for Keys

I noticed some scripts like evil.py, which contained AES decryption code. After examining previous commits, I discovered three decryption keys:

key1: git_with_x
key2: or_cenriv
key3: btuecieurbc

------------------------------------

Step 6: Decrypting the Encrypted Text with Discovered Keys

I found that the encrypted text in evil.py was decrypted using AES (ECB mode). I combined the keys and executed the following code:


zeroday{g1t_x4r_4nd_p455w0rdsss}

