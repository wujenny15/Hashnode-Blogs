## Linux Command Line Interface Cheatsheet

## File and Directory Naming Convention
* case sensitive
* best is all lowercase
* vi/ vim is a  default editing program
:w -> Enter

## General
```bash
# Clear the terminal screen
clear

# Show the command history
history

# View the on-line reference manual pages for the commands/programs
man grep
man mkdir
```

## Directory Operations
```bash
# Show working directory
pwd

# Make directory dir
mkdir dir

# Change directory to dir
cd dir

# Return to the parent directory
cd ..

# List all files
ls

# . means the current directory
./hello.sh
```

## ls Options
```bash
# Show all files (including hidden)
-a

# Sort by last modified
-t
```

## File Operations
```bash
# Create file1
touch file

# Concatenate files and output
cat file1 file2

# Copy file1 to file2
cp file1 file2
//'..' means the destination directory
cp bird.txt .. 

# Move file1 to file2
move file1 to file2

# Delete file1
rm file1
//rm -r mallDirectory -> '-r' means the directory
# mkdir -p -> '-p' means the parent directory

# View the content of the file
cat file1.txt

# Print text into file
echo "This is a test" > test1.txt

# View files
# Press q to quit less and return to the command line
less test1.txt
more test1.txt
```

## Nano Shortcuts
More nano info at: [ http:/­/ww­w.n­ano­-ed­ito­r.o­rg/­doc­s.php](http:/­/ww­w.n­ano­-ed­ito­r.o­rg/­doc­s.php) 
```
# Open file
nano file.txt

# Read file
Ctrl+ R

# Save file
Ctrl+ O

# Close file
Ctrl + X

```

## Environment
```bash
# Global env config files
/etc/profile
/etc/bash.bashrc

# User env config files
~/.bashrc
~/.zshrc

# Show environment variables
env 

# Print defined env vars
printenv

# Make a VAR available to child process
export VAR

# Load a file into current script or shell session
source ~/.zshrc
```

## Bash Shortcuts
```bash
# Quit the program
Ctrl + C
```

## File path
```BASH
# Relative Paths
cat mall/../../menu.txt 

# Absolute Paths
#  / means the root directory
cd / 
cd /home
```

## Wildcard Expansion
```BASH
*.txt
echo re*.txt
```

## Search Files
```bash
# Search for pattern in files
# Search through files for lines that contain a certain string
grep pattern files

# Case insensitive search
grep -i

# Show matched part of file only
grep -o

# Find files starting with name in dir
find /dir/ -name name*
```


