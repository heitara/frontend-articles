# Terminal 
  1. **Basic commands:**
   
  - `mkdir` [OPTION]... DIRECTORY... -> The command stands for "Make directory" and allows users to create directories. We can create more than one directory at a time.
    - `mkdir test` // It's going to create a folder with the name test.
    
- `cd` -> Changes directories!
    - `cd Movie` //It's going to change to Movie folder.
    - `cd ..` //Change to previous directory(parent directory).
    - `cd .` //Change to current directory.
    - `cd ~` //Change to the HOME direcory of the user that's currently logged in.
    - [How to use cd & ls](https://www.youtube.com/watch?v=5QQoKZamqpU&list=LL&index=2)
    
- `echo` [option] [string] -> The command is going to display string or variable provided by the user.
    - `echo -e` //Enables interpretation of escape charecters like: \a, \b, \c etc.
       - `\a` -> plays a sound alert when displaying the output.
       - `\b` -> creates a backspace character.
       - `\c` -> omits any output following the escape charecter.
       - `\n` -> adds a new line.
    - `echo -n` //It's going to display the content with line numbers.
   
- `cat` [option] [directory] -> The command can:
   - Display content of a file(s) -> `cat test_file.txt` or for multiple files `cat test_file1.txt test_file2.txt`
   - Redirect contents -> `cat file1.txt > file2.txt`
   - Append content from one file to another -> `cat file1.txt >> file2.txt`
   - Append text -> `cat >> file.txt`
   - Create new file -> `cat > new_file.txt`
   - [How to use `cat`](https://www.youtube.com/watch?v=nK4028I3N5U&list=LL&index=3&t=452s)
   
- `ls` [option] [directory] -> The command is used to view the content of a directory. If we want to see the content of other directories, type ls and then the directory’s path.
   - `ls -R` -> It's going to list all the files in the sub-directories.
   - `ls -a` -> It's going to show the hidden files
   - `ls -al` -> It's going to list the files and directories with detailed information like: permissions, size, owner, etc.
   - [How to use cd & ls](https://www.youtube.com/watch?v=5QQoKZamqpU&list=LL&index=2)
 
- `grep` or Global Regular Expression Print -> The command it's going to search through a file or files for a regular expression(regex) and then print out the lines where that regex was found.
   - `grep 'orage' grocery_list.txt` //It's going to search for orange in the .txt file -> oranges-yes, Orange Juice-no
   - `grep -i 'orange' grocery_list.txt` // -i it's going to ignore upper or lower-cased latters -> oranges-yes, Orange Juice-yes
   - `grep -w 'orange'.... ` // It's going to return only the lines where our regex is a single word -> oranges-no, orange juice-yes
   - `grep -c .... ` // -c It's going to return how many times our regex was found (stands for count)
  
#
2. **vim**
 
- Create:
> To use and create vim file (in VScode) we need: Vim extension and [enabled key-repeating](https://github.com/VSCodeVim/Vim).

##### Edit file:
- Switching modes:
   - `i` for insert mode.
   - `esc` for command mode.

- Navigation in command mode:
  - `k` for going up.
  - `j` for going down.
  - `h` for going left.
  - `l` for going right.
 
- Editing in a line:
  - `Shift + i` -> Switch to insert mode and move to the start of the line.
  - `a` -> Switch to insert mode and move to the right.
  - `Shift + a` -> Switch to insert mode and move to the end of the line.
  - `i` -> Switch to insert mode and move to the left.
 
- Making changes while in command mode:
  - `x` -> Delete the character that we are currently on.
  - `r` -> Replace the character that we are currently on.
 
#
3. **ssh**

> SSH (or Secure Shell) is network protocol that allows one computer to secuerly connect to another computer by encrypting data. It's commonly implemented using the clinet-server model:
- One computer is called SSH Clinet and another machine acts as SSH Server.
- Then SSH can be set-up by using a pair of keys:
   - Public key that is stored on the SSH Server and a private key that is stored on the SSH Clinet.
- Then the SSH Client will make contact with the SSH Server and provide the ID of the key pair to prove it's identity.
- The SSH servers creates a challenge that is encrypted by the public key and sent to the SSH Client.
- At last the SSH Client decrypts the callenge with the private key and sends back the original form to the SSH Server.
- Once the nagotiation is complete, the connection is established.

 
---