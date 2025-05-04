
# Shell Commands and Scripting Cheat Sheet

This README provides a quick reference to 
##### 1.common shell commands,
##### 2.regular expressions, 
##### 3.special characters, 
##### 4.basic `vi` editor usage,
##### 5.shell scripting fundamentals, and examples for practical use.

---

## 1. Common Shell Commands with Examples
    ls -l # List files in long format

    cd /home/user # Change directory

    chmod +x script.sh # Make a script executable

    grep "error" logfile.txt # Search for 'error' in a file

    find . -name "*.sh" # Find all .sh files recursively

    cat file.txt # Display file content

    sed 's/apple/orange/g' file.txt # Replace all 'apple' with 'orange'

    awk '{print $1}' file.txt # Print the first column of each line

    mkdir new_folder # Create a new directory

    rm file.txt # Remove a file

    cp file1.txt file2.txt # Copy file1.txt to file2.txt

    mv file.txt /tmp/ # Move file.txt to /tmp directory

    head -n 10 file.txt # Show first 10 lines of file.txt

    tail -f /var/log/syslog # Follow log file in real-time

---

## 2. Use of Regular Expressions (Regex)

- `^` : Start of line  
- `$` : End of line  
- `.` : Any single character  
- `*` : Zero or more occurrences  
- `[]` : Range or set of characters  
- `\` : Escape special character  

Example with `grep`:

    grep "^a.*z$" file.txt # Lines starting with 'a' and ending with 'z'

    grep -E "^[A-Za-z]+@[A-Za-z]+.[A-Za-z]{2,}$" emails.txt # Match valid email format

---

## 3. Special Characters in Shell

- `*` : Wildcard (matches any number of characters)  
- `?` : Single character wildcard  
- `$` : Variable prefix  
- `|` : Pipe (pass output of one command as input to another)  
- `;` : Command separator  
- `&` : Run command in background  
- `\` : Escape character  

Example:

    ls *.txt | grep "report" > output.txt & # List .txt files containing 'report', save output, run in background

---

## 4. Matching Characters with `grep`

    grep "[0-9]" file.txt # Lines containing digits

    grep "[aeiou]" file.txt # Lines containing vowels

    grep "[^a-z]" file.txt # Lines not containing lowercase letters

---

## 5. Pipes and Filters Example

    cat access.log | grep "404" | wc -l # Count number of 404 errors in log file

    ps aux | grep apache # Find all processes related to apache

    df -h | grep "/dev/sda1" # Show disk usage of specific partition

---

## 6. Basic `vi` Editor Commands

- Open file:  
    
      vi filename.txt

- Editing modes:  
     `i` : Insert mode  
- `Esc` : Exit insert mode  

- Save and quit:  
      `:w` : Save  
      `:q` : Quit  
     `:wq` or `ZZ` : Save and quit  

- Navigation:  
     `h, j, k, l` : Move cursor left, down, up, right  
     `gg` : Go to top of file  
     `G` : Go to end of file  
     `/word` : Search for "word"  

- Insert and delete lines: 

        echo "New Line" >> file.txt # Append line outside vi
        sed -i '2i\Inserted line' file.txt # Insert at line 2
        sed -i '3d' file.txt # Delete line 3 

- Replace text:

         :%s/old/new/g # Replace all 'old' with 'new' in vi
         sed 's/old/new/g' file.txt # Replace in file using sed

---

## 7. Shell Scripting Basics

### Set Commands
    set -x # Enable debugging (show commands as executed)
    set +x # Disable debugging

### Variables

    name="Suchithra"
    echo "Hello $name"

### Arrays

    arr=(apple banana cherry)
    echo ${arr} # banana
    echo ${arr[@]} # All elements

### Operators and Arithmetic

    a=5; b=3
    echo $((a + b)) # 8
    [[ $a -eq $b ]] && echo "Equal" || echo "Not equal"

### Decision Making

    if [ $a -gt $b ]; then
    echo "a is greater"
    else
    echo "b is greater"
    fi

### Loops

**For loop:**

    for i in 1 2 3; do
    echo $i
    done

**While loop:**

    count=1
    while [ $count -le 5 ]; do
    echo $count
    ((count++))
    done

### IO Redirection

    echo "Output" > file.txt # Overwrite file
    echo "Another" >> file.txt # Append to file
    cat < file.txt # Read from file

### Shell Functions

    greet() {
    echo "Hello, $1!"
    }
    greet Suchithra

Call another script from a script:

    script1.sh
    ./script2.sh

---

## 8. `awk` Program Example

Print names of users with salary > 50000 (assuming file format: Name Dept Salary):

    awk '$3 > 50000 { print $1 }' employees.txt

Additional `awk` examples:

    awk '{print $2, $1}' file.txt # Print 2nd and 1st columns swapped
    awk '/error/ {print $0}' logfile.txt # Print lines containing 'error'

---

## 9. Additional Useful Commands and Examples

Check disk usage of current directory

        du -sh .

Display environment variables

        printenv

Show last 10 system log entries

        tail -n 10 /var/log/syslog

Download a file from the internet

        wget https://example.com/file.zip

Compress a directory

        tar -czvf archive.tar.gz /path/to/dir

Extract a tar.gz archive

        tar -xzvf archive.tar.gz

        












