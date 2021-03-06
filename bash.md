# Bash
* File names starting with . makes file hidden
* Mac OS file names are not case sensitive (by default)
* File extensions are optional on Unix

### Quoting, Escaping
* Backslash escapes a single character
* Single quotes - Escape all characters between them

### Paths
* Absolute paths start with / (which is root)
* Relative paths don't start with / and are resolved relative to current directory

### Commands
```
ls -R // Lists whole directory recursively
cp -R // Copies everthing in the subdirectories recursively
open . // Opens current working directory in Finder
```


### Bash wildcards 

* \* matches anything, including nothing at all 
* ? matches exactly a single character 
* [] matches one of the characters in the list, for e.g. [acd7_] would match either a, c, d, 7, or _ character and nothing else. You can negate the list of characters by starting the list with ^ character. Ranges work well too, for e.g. [a-z], [0-9], [A-C3-9]

  

### Brace Expansion 
* Helps with generating strings, its syntax takes following form: pre{list,of,string}post 
* Bash would expand each string within curly brace with pre and post string, for e.g. touch {a,b,c}.txt would be expanded to touch a.txt b.txt c.txt 
* Brace expansion comes before wildcard expansion 

  

### Output Redirection 
* \> You can redirect standard outout stream using greater than command > it saves output of command to file, for e.g. ls > listing.txt saves output of ls command to file listing.txt 

* \>> Appends output to end of file 

  

### Pipe  
* Sends output of one program as input to another program 


### Command Substitution  
* Replace a command with its output 
* Put command between $() for e.g. echo "hello ${whoami)" would result in bash executing whoami command and replacing it in echo command 


### Jobs and Processes  
* To run a command in background append & at the end and that would cause bash to run it in the background so that user can continue using terminal. 
* To avoid getting any output from background command printed on screen, redirect its output to a file by using > command 
* Background jobs can't read input from user, hence its best to only run those programs in background that don't need user input 
* ^Z suspends a running job, after suspending a job use fg to bring job to foreground or bg to send it to background 
* To kill a foreground program use ^C 
* Use kill command to end any program (can only end processes you own), for e.g.  
```
    kill %2 // would kill job id 2 

    kill %cp // would kill cp program 

    kill 3344 // would kill process with id 3344 
```
* Use jobs command to see list of all running jobs 
* Use ps command to see list of all running processes under a terminal
