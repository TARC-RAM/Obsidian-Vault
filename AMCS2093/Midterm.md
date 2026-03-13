#### Module 1 Performing Basic Linux Tasks (Minimal scope)
who - Displays currently logged-in users
whoami - Displays your login name
id - Displays the number associated with your user account name and group names; these are commonly referred to as User Ids (UIDs) and Group (GIDs)
uname -a - Displays system information

date - Displays the current date and home
- date -s 'datestr'
	- date -s '11/20/2026 12:48:00'

cal - Displays the calendar for the current month
- cal month year
	- cal 12 2025


#### Module 2 Managing Files in Linux (Majority scope)
touch
- touch -m -t YYYYMMDDhhmm file.txt

more / less
- Space displays the next page
- Enter displays the next line

head - used to view the first lines of a file
- head -n 5 (shows the first 5 lines)

tail - shows the last lines of a file
- tail -n 20 file.txt (Shows **last 20 lines**.)
- tail -f (prints the new content as it is being written)

cat
- cat > file (enters a overwriting mode. **OVERWRITES ALREADY WRITTEN CONTENT**. Ctrl + D to exit)

hard link
- ln file link (file is the orignal file name)
- ls -li (shows the same INODE number as the original.)

Soft links (symbolic links)
- ls -l file link

find - as suggested by the name
- find [path] [conditions] [actions]
	- find . -name "file.txt"
	- - `.` → start in current folder
	- `-name` → match filename
	- `"file.txt"` → exact match (case-sensitive)
- find ~ -name “file2” –type f –exec rm {} \;
	- -exec [command] \;
	- rm {}
		- {} is a placeholder for everything find identifies so file1 file2 file3 goes into the place holder and deleted.
- -iname (case insensitive match)
	- Will match `file.txt`, `File.txt`, `FILE.TXT`, `fIlE.TxT`, etc.
- -size +10M
	- - `+10M` → bigger than 10 MB
	- `-10M` → smaller than 10 MB
- grep
	- -i (insensitive search)
		- grep -i error file.txt
			- Error, ERROR, ErRoR, error
	- -n (Show Line Numbers)
		- file : line : word
	- -v
		- shows everything that does not contain search string
	- -r
		- Just searching everything in a folder
	- -l searches the file for the word and returns the file name only
- egrep
	- just doesnt need that accurate wording.
	- egrep "(cat|dog)s?" pets.txt
		- cat 
		  cats 
		  dog 
		  dogs