## Cheatsheet: Command-Line Interface (CLI)

## Introduction
This is a simple guideline and takeaway for reference.

## List files Command
Ctrl+C -> quit the program <br>
ls -> listing the files ->  <br>
ls -a (list all the files including hidden files)<br>
ls -a -t (-t -> timestamp)<br>
ls --all<br>
cat -> take the files and concacencate -> cat 'fileName'<br>
clear -> clear the output<br>
echo -> <br>

## Shortcuts
cat <br>
history -> show the command history<br>
press tab can auto complete<br>


## Directories
pwd -> printing working directory<br>
cd<br>
ls -> listing all files<br>
cd .. -> return to the parent directory<br>

## Relative Paths
cat mall/../../menu.txt <br>

## Absolute Paths
cd / -> '/' means the root directory<br>
cd /home<br>

## Directory Shortcuts
./hello.sh -> '.' means the current directory<br>
cd ~ -> return to the last directory<br>

## Wildcard Expansion
*.txt<br>
echo re*.txt<br>

## View Files by Less
less a.txt<br>
q -> quit<br>
more a.txt<br>

## Working with files
* ls
* copy <br>
cp bird.txt pigeon.txt<br>
cp bird.txt .. ->'..' means the destination directory <br>

* move <br>
mv bird.txt sparrow.txt<br>

* remove <br>
rm -r mallDirectory -> '-r' means the directory<br>

* make <br>
mkdir -p -> '-p' means the parent directory<br>

## Files and Directory Naming Convention
case sensitive<br>
best is all lowercase<br>

## Manual 
man<br>
q -> quit<br>

## Other
find -> recursively search<br>
grep 'Windows' -> search through files for lines that contain a certain string<br>
vi -> default editing program<br>
vim<br>
:w -> Enter<br>

nano -> available on Linux<br>
nano file.txt<br>