# Exercise Answers

##Project Assignment Beginner 1
1. Write the command that will allow you to navigate to two directories above your current directory.

	```
	cd ../../
 	```
2. Write the command and flag that will list the files and directories inside of your current directory.
	 
 	```
   	ls -p
  	```
3.  Write the command and flag that will list all of the files and directories in your current directory in long-format.

	```
	ls -l
	```
4.  Write the command and flag that will list all of the files and directories in your current directory, including hidden files

	```
	ls -a -p
	```
5. Write the command that will create a folder in your current working directory and name it clean_code_examples.

	```
	mkdir clean_code_examples
	```
6. Write the command to create a new file. Give the file a name and use the .txt extension

	```
 	touch anynamethatidlike.txt
	 ```
7. Write the command that will output the contents of the file socks to buy.txt, located in your current working directory, to the terminal. Assume that either socks to buy.txt already exists, or create it yourself.

	```
 	touch socks\ to\ buy.txt ; echo "I should wait to buy socks until next Fall." >> socks\ to\ buy.txt ; cat socks\ to\ buy.txt
	 ```
8. Write the command to display your Present Working Directory.

	```
	 pwd
	 ```
9. Write the command to output the current user to the terminal. The current user is generally the account that is logged into the operating system and currently using the terminal.
	
	```
	 whoami
	 ```
10. Write the command to list the files and folders of the folder two above your current directory. For example, if you are in C:/Users/John Wayne/My Documents/Tax Forms/, display all files and folders within the directory C:/Users/John Wayne/.

	```
 	ls -p ~/Coursework
	 ```
11. Write the command to create the file list of best cat pictures.html.

	```
	 touch list of best cat pictures.html
 	```
12. Write the command that will change your current directory to C:/Users/Default User/My Documents. Note: the directory C:/Users/Default User/My Documents may not exist on your computer; if that is the case, you’ll see the error bash: cd: C:/Users/Default User/My Documents: No such file or directory

	```
 	cd /Users/Default User/My Documents
 	```
13. Write the command that will ping the ip address 8.8.8.8.

	```
	 ping 8.8.8.8           // break with Ctrl + c
	 ```
14. Write the command to change your current directory to the folder /documents/, where is the single character shortcut for $HOME.

	```
 	cd ~/Documents
	 ```
15. Use the echo command to display the text “My name is ” followed by your first name. View the help or man pages for echo to learn the command’s arguments man echo, help echo or echo --help.

	```
 	echo "My name is Magnus"
	 ```
16. Write the command that will show the output of two files, one after another: tylers favorite songs.txt and sarahs favorite songs.txt.

	```
 	cat tylers favorite songs.txt sarahs favorite songs.txt
	 ```
17. Write the command to show the help, or manual, for the echo command, and add it to a file called echo_options.txt.
	
	```
 	help echo > echo_options.txt
 	```
18. Write the command, flag, and flag option to ping 127.0.0.1 two times. A flag option is an option passed immediately after a flag.

	```
	 ping 127.0.0.1 -c 2
	 ```
19. Write a single command to display the contents of all Markdown files (that have the extension .md) to the console.

	```
 	more *.md
 	```
20. Write the command to remove the file yesterdays_todo_list.md from the directory you are presently working in.

	```
 	rm yesterdays_todo_list.md
 	```

##Project Assignment 2: Intermediate
1. Use only the command line to create 5 files (one at a time) and add full sentences to each, as illustrated below:
Create the file myname.md and write your name in it.
Create the file myfavoritefoods.md and write your three favorite foods.
Create the file dreamproject.md and write about a project that you would like to build after Modern Developer.
Create the file music.md and write the genre of music, song, or artist, that you feel most comfortable listening to.
Create the file colors.md and write your favorite color, or colors.
	
	```
	echo "Magnus Croneborg" > myname.md
	
	echo "Lasagne Biff Steak with bearnaise sauce Spagetti Carbonara Kebab" > myfavoritefoods.md
	
	echo "I would like to build a site for a big company with a lot of cool javascript. The site should also contain an online 	webshop and I would like to make it interactive in some way" > dreamproject.md
	
	echo "I love to listening to Adele, she write fantastic songs and she also got humour." > music.md
	
	echo "Red, Blue is my favourite colors." > colors.md
	```
2. Find out which of the files that you wrote in the previous step had the largest file size. Write the command and the correct flags to list the files and their file size in human readable and long format. Then add the output to this file: filesizes.txt.

	```
	ls -l -S -h > filesizes.txt
	```
3. Let’s create a backups folder and backup the files we’ve written so far. Create a new directory and name it backups. Use the tar command to archive the contents of your commandline-practice folder. Name your archived file backup1.tar, and save it inside your backups folder.

	```
	mkdir backups | tar -czf backups/backup1.tar *.md *.txt

	```
4. Create a file sites.txt and add to it a list of your favorite websites, each on its own line. You’ll need to type the newline character (\n), and the echo flag that enables interpretation of backslash escapes.

	```
	echo -e "learn.moderndeveloper.com\njavascriptissexy.com\ngetify.me\ngithub.com\nalistapart.com" > sites.txt
	```
5. Use curl to get the contents of http://yahoo.com and store it inside a file, yahoo.html. When you request the file, it will retrieve the web page of the first web server that responds, which in this case is a server telling you the web page has been relocated. This is a normal occurrence on the web; it is called a redirection. You will learn more about server redirects in an upcoming course. Use the -L flag to follow the redirection and receive the correct page

	```
	 curl -L study.moderndeveloper.com > study.html
	```
6. Use the mv command and Command Escaping to rename your backup archive. Then navigate to the backups directory and rename your backup1.tar archive to output of the date command. That is, whatever the output (the text) of the date command is, use that text as the new name for your backup1.tar file.

	```
	cd backups ; mv backup1.tar "$(date)"
	```
7. Use the wc command and the correct flag to determine how many words you wrote inside your dreamproject.md file. If the file contains fewer than 20 words, append another two sentences to the file. Use those two sentences to describe your dream project.

	```
	wc -w dreamproject.md               -> output 36 dreamproject.md
	```
8. Use the grep command to find the number of JavaScript files inside your yahoo.html file by searching for “.js“. Save the result to a new file, javascripts.html.


	```
	grep -oc "\.js" study.html > javascripts.html              -> output 9
	```
9. Let’s find out the total number of words inside of the text files (.txt) that you created. Use the cat command to list all of the contents of the text files inside of your commandline-practice folder; then pipe (|) the output of the cat command to the word count program (wc).

	```
	cat *.txt | wc -w					-> output 61 words
	```
10. Your workspace has undergone many changes since your last backup. Create another backup file using tar and the directions in exercise 3; name your backup backup2.tar. Let’s clear out the workspace. find all Markdown files, html files, and text files, and remove them by passing the -delete flag to your find command. Be careful to not delete your backups folder.

	```
	tar -czf backups/backup2.tar *.md *.txt *.html && find . -type f \( -name "*md" -o -name "*txt" -o -name "*html" \) -delete
	```

##Project Assignment 3: Advanced
1. Create a script, titled mdextract, that will extract, or expand, a tar archive into a new directory. Extracting an archive reverses the archive process, re-creating the files that were originally passed to tar. Write mdextract to have two passed-in options: the path to the archive, and the path where the archive will be extracted to. Use the mkdir command and any necessary flags to create the directory, if the directory does not exist.
Note: We have not discussed extracting archives. You will need to refer to tar’s man or help pages to learn to do that. But don’t use Google to find the answer. The answer is right there in the tar’s man pages. Read it; you will see.

	```
	iMac:~ Magnus$ cd commandline-practice/ && mkdir scripts/ && cd scripts/
	iMac:scripts Magnus$ cat > mdextract
	
	#!/bin/bash
	# Extracts a tar archive from one directory to another
	# The script uses positional parameters for path/to/archive.tar("$1")
	# and extracts archive to a new directory ("$2")
	
	Echo "Extracting a tar archive from $1 to $2."
	if [ -d "./$2" ]
	then
    	echo "Directory already exist."

	else
   	 mkdir $2
	fi
	
	#In x mode, -C change directories after opening the
	#archive but before extracting entries from the archive.
	
	tar -xvf $1 -C ../scripts/$2
	Echo "done"
	iMac:scripts Magnus$ chmod +x mdextract
	iMac:scripts Magnus$ ./mdextract ../backups/backup2.tar backup2
	Extracting a tar archive from ../backups/backup2.tar to backup2.
	x colors.md
	x dreamproject.md
	x music.md
	x myfavoritefoods.md
	x myname.md
	x filesizes.txt
	x sites.txt
	x javascripts.html
	x study.html
	done
	iMac:scripts Magnus$
	
	```
	
2. Create a script titled mdtemplate that will create the file structure of a website. Write your mdtemplate script to have the following positional parameters:
 	* $1, the name of a new directory where your template files will be created
 	* $2, a title, which will be used inside your template index.html for the HTML document title, and an h1 tag

		Design your mdtemplate so that it creates the following files inside of the new folder:

	* A css directory
	* An images directory
	* A js directory
	* A style.css file inside of the css directory
	* A main.js file inside of the js directory
	* An index.html file, which should be a completely valid HTML5 document
	* Include a CSS ruleset inside of style.css, and include an h1 element inside of your index.html
	
	
	```
	iMac:~ Magnus$ cd commandline-practice/scripts/
	iMac:scripts Magnus$ cat > mdtemplate
	
	#!/bin/bash
	#Create a directory where the html_template will be created
	
	mkdir $1 $1/images $1/css $1/js

	cat > $1/index.html <<- EOF
	<!DOCTYPE html>
		<html lang="en">
			<head>
				<meta charset="utf-8">
				<title>$2</title>
				<link rel="stylesheet" href="css/style.css" type="text/css">
			</head>
		<body>
			<h1 id ="colorize">$2</h1>
				<p>Made by $USER</p>
			<script src="js/main.js"></script>
		</body>
		</html>
	EOF

	cat > $1/css/style.css <<- CSS
	body {
 		background-color: #FF6600;
	 }
	CSS

	cat > $1/js/main.js <<- JS
		document.getElementById("colorize").style.color = "#FFF"
	JS
	
	iMac:scripts Magnus$ chmod +x mdtemplate
	iMac:scripts Magnus$ ./mdtemplate LearnSite "Created by Magnus"
	
	```
3. Create a script named web_bundler that concatenates—or adds the contents of—all files of a specified type, from a specified directory, into a single file.Create web_bundler to have the following positional parameters:

	* $1, the name of the output file.
	* $2, the find pattern, which tells the script which file path to follow, and which file names to bundle. Examples of file patterns include *.html, *.txt, and template-*.
	
	
	```
	iMac:~ Magnus$ cd commandline-practice/scripts && mkdir backup2/partials/ 
	iMac:scripts Magnus$ cp ./backup2/*.md ./backup2/partials/
	iMac:scripts Magnus$ cat > web_bundler
	#!/bin/bash
	#Concatenate and bundles all files with a specified type from a specified directory
	cat $2 >> $1
	
	iMac:scripts Magnus$ chmod +x web_bundler
	iMac:scripts Magnus$ ./web_bundler bundled.md ./backup2/partials/"*.md"
	```


 

