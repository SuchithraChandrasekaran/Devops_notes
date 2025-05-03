
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












