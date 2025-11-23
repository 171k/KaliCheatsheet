# Kali Linux Commands Cheatsheet For Beginners!

This cheatsheet summarizes essential Kali Linux commands useful for CTF challenges.

Will update this cheatsheet from time to time! 

---

## 1. File & Directory Management

### **ls** - list directory contents

```bash
ls                # basic listing
ls -l             # long listing
ls -a             # include hidden files
ls -h             # human-readable sizes
ls -R             # recursive listing
```

### **cd** - change directory

```bash
cd /path/to/folder    # navigate to folder
cd ..                 # go up one level
cd ~                  # go to home
cd -                  # go to previous directory
```

### **mkdir** - create directories

```bash
mkdir new_folder        # create folder
mkdir -p dir/subdir     # create nested folders
```

### **touch** - create empty files / update timestamps

```bash
touch file.txt
touch -t insert_time file.txt #example: touch -t 200305291200 birthday.txt
```

### **cat** - concatenate / view file contents

```bash
cat file.txt
cat file1.txt file2.txt > newfile.txt  # combine files
```

### **nano** - edit/create files

```bash
nano file.txt
nano file1.txt file2.txt #edit 2 files
```

### **find** - search for files

```bash
find /path -name "filename"            # exact match
find /path -iname "*flag*"             # case-insensitive wildcard
find /path -type f                      # files only
find /path -type d                      # directories only
find /path -size +10M                   # files bigger than 10MB
find /path -mtime -1                    # modified in last day
find /path -perm -4000                  # SUID files (privilege escalation)
find /path -user root                    # owned by root
find /path -executable                   # executable files
find /path -name "*.log" -exec rm {} \;  # execute command on found files

or
find | grep file_name #for CTF chall to find files inside folder
```

### **locate** - fast file search (uses database)

```bash
locate filename
updatedb     # update database before searching
```

## 2. File Inspection



### File - inspect file type

```bash
file file_name 
```

### **xxd** - hex dump / reverse

```bash
xxd file.bin           # hex + ASCII view
xxd -r file.hex file.bin   # reverse hex to binary
xxd -c 16 file.bin      # 16 bytes per line
```

### **less** - scrollable file viewer

```bash
less file.txt
# navigate with arrows, search with /keyword, quit with q
```

### **strings** - extract readable text from binaries

```bash
strings binaryfile
```

### **file** - detect file type

```bash
file filename
```

## 3. Archives & Compression

### **zip** - create compressed archives

```bash
zip archive.zip file1 file2
zip -r archive.zip foldername/   # recursive
zip -P password archive.zip file.txt  # password-protected
```

### **unzip** - extract archives

```bash
unzip archive.zip
unzip archive.zip -d extracted_folder
unzip -P password archive.zip
```

**Tip:** Can unzip files renamed with different extensions (`.apk`, `.jar`, `.docx`, `.pdf`) if they are ZIP-based.

## 4. System & Permissions

### **whoami** - current user

```bash
whoami
```

### **sudo** - run command as superuser

```bash
sudo command
```

### **chmod** - change file permissions

```bash
chmod 755 script.sh    # rwxr-xr-x
chmod +x script.sh     # make executable
```

### **grep** - search text in files

```bash
grep "pattern" file.txt
grep -r "pattern" /path/to/folder  # recursive
```

### **cp / mv / rm** - copy, move, delete

```bash
cp file.txt /destination/
mv file.txt newname.txt
rm file.txt
rm -r folder/  # remove directory recursively
```

---

This cheatsheet is made for beginner, feel free to contact me if there is misinformation!
