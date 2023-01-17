# A Tutorial on How to Connect To Remote Server for CSE 15L
by Kay Qu

***

In this tutorial, we will be providing a step-by-step guide on how to connect to a remote server via a course-specific account on *ieng6* .

***

## Step 1: Download VSCode

**Note**: If you do not wish to download external apps onto your PC, you can use the PCs located in the CSE building's basement and proceed to the next step.

1. Go to Visual Studio Code's [official website](https://code.visualstudio.com/) and download the environment that suits your working environment (e.g. MacOS, Windows, Linux, etc.)

***

2. Launch Visual Studio Code (you should see the welcome page)
![Screen Shot 2023-01-12 at 12 13 44 PM](https://user-images.githubusercontent.com/104349171/212789306-17c732ca-9b96-4de9-8f20-c8f6bff0a370.jpg)

***


3. On the option bar on top, find **terminal** tab and click **new terminal**. You should see a terminal tab show up on the bottom. (You should see something like this)
![Screen Shot 2023-01-16 at 5 23 04 PM](https://user-images.githubusercontent.com/104349171/212789444-f204602a-e8c0-463b-8c38-d7a5614aaa6f.jpg)

***

4. Find your CSE 15L Student Code. You can look up your course-specific account for CSE15L [here](https://sdacs.ucsd.edu/~icc/index.php). Here is the tutorial on how to [reset your password](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit) 

## Step 2: Remotely Connecting
  
1. Go to your terminal. Type `ssh *YOUR_ACCOUNT*@ieng6.ucsd.edu` (e.g. `ssh cs15lwi23zz@ieng6.ucsd.edu`)

2. The server will ask for your password by showing `Password: `. Enter the password (note that what you enter will not be present on screen) 

3. If successful, you will see this message: 


  `The authenticity of host 'ieng6.ucsd.edu (128.54.70.238)' can't be established.
  RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
  This key is not known by any other names
  Are you sure you want to continue connecting (yes/no/[fingerprint])? y
  Please type 'yes', 'no' or the fingerprint: `

4. Type `yes` to continue. 

4. You are logged in successfully if you see this message:
![Screen Shot 2023-01-16 at 5 39 18 PM](https://user-images.githubusercontent.com/104349171/212791083-e3b3bfb9-1bf5-47ab-bd13-9affae4c114d.jpg)


## Step 3: Trying Some Commands

Here are some great examples of terminal commads to try ([reference](https://ucsd-cse15l-w23.github.io/week/week1/#part-5--run-some-commands)):


`cd ~`

`cd ..`

`cd`

`ls -lat`

`ls -a`

`ls <directory>` (where <directory> is /home/linux/ieng6/cs15lwi23/cs15lwi23abc, where the abc is one of the other group members’ username)
  
`cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`
  
`cat /home/linux/ieng6/cs15lwi23/public/hello.txt`
  
  example:
  ![Screen Shot 2023-01-16 at 5 46 08 PM](https://user-images.githubusercontent.com/104349171/212791788-aabe9cc5-61ee-4af5-a209-d4f80a910e0f.jpg)

  
