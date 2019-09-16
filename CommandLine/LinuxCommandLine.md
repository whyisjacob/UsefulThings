# Useful Items
### Linux Command Line Prompt
#### Upload/Download files from remote server
 - How to download a file from remote server using SSH
	 - `$ ssh host 'cat /path/on/remote' > /path/on/local`
 - How to upload a file from local to remote server
	 -  `$ scp /path/on/local username@host:/path/on/remote`
	 - This one may only allow you to upload to the root of the remote server. After which you will have to move it to the desired location.
#### Search contents inside a file
 - How to "Grep", or search for a file
	 - `$ grep "information" file/path/name.txt`
		 - To store the result of the above grep command into a file named result.txt, use this command
		 - `$ grep "tom@anydomain.tld" /file/path/name.txt > /file/path/result.txt`
	 - Should the file be compressed with an extension of `.gz` use the following `zgrep` command
	 - `$ zgrep "information" file/path/name.txt`
#### View Files
 - How to view files
	 - There are a few different ways to view files on a server. One of the most simple ways is to use the `cat` command
	 - `$ cat /path/to/filename.txt`
	 - `$ less /path/to/filename.txt`
	 - What's the difference between cat and less?
	 	 - Cat is a command that lets you quickly view the file. A benefit of cat is it opens, displays, and then closes the file leaving the display up. so you can move onto other commands without having to manually close the file
		 - Less is used when you want to quickly open the file and be able to perform simple functions while the file is open. Such functions include
		 	 - Search for text from within the file
				 - `/ "text in quotations" + enter`
			 - Quickly move to the end of the file
			 	 - `G`
			 - Quickly move to the beginning of the file
			 	 - `gg`
			 - Close the file
			 	 - `q`
 - How to unzip files 
	 - `$ gzip -d path/to/file.txt`
	 	 - Note: you may need to use the `sudo` command
#### Log Files
 - The most important command is "tail". Tail can be used to read the last lines from a file. 
	 - `$ tail -n 100 /file/path/mail.log`
 - To get all newly added lines from a log file in realtime on the shell, use the command
	 - `$ tail -f /file/path/mail.log`
 - If you want to get the last 1000 lines from a log file and they do not fit into your shell window, you can use the command "more" to be able to view them line by line.
	 - ` $ tail -n 1000 /file/path/mail.log | more`

#### Bash Aliases
 - It's useful to create aliases for commonly used commands
	- https://www.digitalocean.com/community/tutorials/an-introduction-to-useful-bash-aliases-and-functions