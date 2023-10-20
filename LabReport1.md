
## **Lab Report 1**



# cd
![image](https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/e696aef1-eabb-4f50-b6f6-005ed31e36ed)

- **No Arguments:**
The argument for cd remained the same and nothing happened since it was run in the home directory. Since cd changes the working directory and no directory is called, it doesn't output anything. This output is an error because no directory was provided, meaning no directory to change to.
- **Path to Directory:**
Since cd was run in the home directory, there was no output since cd does not print anything. When we call a path to the cd directory, the path changes, adding "/lecture1" to the end and now the argument is in lecture1. There is no error here.
- **Path to a File:**
Since cd is already in the directory path, we can try calling a file within lecture1, for example, when we call "README", it displays "Not a directory". Cd is used to change directories and not files. This gives an error because README is a file and not a directory. 

# ls
![image](https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/246e6273-6a97-4c70-b7d7-ad7242c14720)

- **No Arguments:**
This command is run in the home directory. When it is called, it displays lecture1 since ls is responsible for outputting all the things contained in the working directory. There is no error present. 
- **Path to Directory:**
When we ls into lecture1, we get an output display for all the files and directories contained in lecture1. Essentially it is the same output as the previous command, but the output is more detailed and specialized since we are now in the lecture1 directory. There is no error here.
- **Path to a File:**
 Calling ls lecture1/README will just display the same content "lecture1/README" as the output. Just like cd, ls does not work on files since files do not contain directories or other files within them. As a result, it just outputs the same input. This is an error.

# cat
<img width="378" alt="Screenshot 2023-10-06 at 10 47 52 PM" src="https://github.com/jasmine-le29/cse15l-lab-reports/assets/116687332/73fd7ab3-b57e-4648-9893-d4b0160eac30">

- **No Arguments:**
- **Path to Directory:**
- **Path to a File:**
- The argument for cat with no arguments is an error display. For the cat function, it is an error since you need an argument for it since there is nothing to display, there will be an error. When we call cat lecture1, it displays that it is a working directory. When cat is called with lecture1/README, it displays on how to use it.
