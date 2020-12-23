# Mac Commands

## Summary

Open the terminal:
1. Cmd + Space
2. Terminal

<br/>

| Command     | Example     | Description |
| ----------- | ----------- | ----------- |
| pwd        | /Users/georgemarklow             |  Print working directory           | 
| cd   | cd or cd ~        | Takes us to the home directory            | 
| | cd <folder name> | Takes us forward one step to the folder that is typed in. | 
| | cd .. | Moves us back one level to the parent folder. |
|  | cd ../.. | Moves us back two levels. Add more /.. for each level we want to navigate up. |
| ls   |         | Show everything in current folder            | 
| clear   |         | Clears terminal out            | 
| mkdir   | mkdir <folder name>        |  Make directory           | 
| touch   | touch new-file.html        |     Create file inside folder        | 
| nano    |         |  Edit file          |
|     |  control + X       |  Exit editor          |
| open    | open new-file.html       |   Open a file or folder          |
| history    |         |  Show all commands that have been run in the current terminal session           |
| cat    | cat /Desktop/new-folder/new-file        |  See contents of file          |
| rm    |         |  Remove file          |
| rmdir    |         |  Remove directory          |
|     |  rm -rf some_dir       |  Force remove directory          |
|     |  rm -fr .git       |  Remove git directory          |
  
<br/>

## Drill

```
➜  ~ pwd
/Users/georgemarklow

➜  ~ mkdir new-folder
➜  ~ cd new-folder
➜  new-folder mkdir new-folder2
➜  new-folder cd new-folder2 
➜  new-folder2 touch new-file.html
➜  new-folder2 nano new-file.html 
'Hello World' + Control+X

➜  new-folder2 cat new-file.html 
Hello World!

➜  new-folder2 open new-file.html
➜  new-folder2 pwd
/Users/georgemarklow/new-folder/new-folder2

➜  new-folder2 cd ~
➜  ~ pwd 
/Users/georgemarklow

➜  ~ cd new-folder/new-folder2
➜  new-folder2 cd ../
➜  new-folder pwd
/Users/georgemarklow/new-folder

➜  new-folder cd new-folder2
➜  new-folder2 cd ../..
➜  ~ pwd
/Users/georgemarklow

➜  ~ cd new-folder/new-folder2
➜  new-folder2 rm new-file.html
➜  new-folder2 rmdir new-folder2
rmdir: new-folder2: No such file or directory

➜  new-folder2 cd ../
➜  new-folder rmdir new-folder2
➜  new-folder cd ~  
➜  ~ rmdir new-folder
➜  ~ cd new-folder
cd: no such file or directory: new-folder
```
