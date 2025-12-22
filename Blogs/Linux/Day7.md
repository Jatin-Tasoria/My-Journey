# Bash Scripting and Automation
Bash Scripting is one of the most important real world Linux skills, especially for:
- System administrators
- AWS EC2 & Cloud Automation.

## Shell Scripting
A shell script is a file containing a series of commands for the shell to execute. The shell itself is a command-line interpreter (CLI), while a shell script is a saved list of instructions (usually with .sh extension) like myscript.sh.

### Shebang Statement
Tells the interpreter which shell program the script is written in.

```
#!/bin/bash
```

### Basic commands
- echo : To print output.
- read : To take input from the user.

### Variables
A variable stores data in memory just like in any programming language.
```bash
name="Jatin"
```
To access it we use:
```bash
echo $name
```
**Rules**
- No space around `=`
- Case-sensitive
- `$` is used to read value

*Array*
```bash
array=("value1" "value2")
```

To access the certain values we use indexes:
```bash
echo ${array[0]}
```

### Conditional Statements
Works just as in any programming language, with minor changes in Syntax.
```bash
if condition
then
  command
else
  command
fi
```

Example:
```bash
if [ -f file.txt ]
then
  echo "File exists"
else
  echo "File not found"
fi
```

### est Conditions ([ ])
[ ] is used to test conditions.
Examples:
- f : file exists
- d : directory exists
- ge : greater than or equal
- gt : greater than
- eq : equals to
- ne : not equals to
- le : less than or equal
- lt : less than

```bash
[ $age -ge 18 ]
```

### Loops
Works just as in any programming language, with minor changes in Syntax.

- for loop
```bash
for i in 1 2 3
do
  echo $i
done
```

- while loop
```bash
while true
do
  date
  sleep 2
done
```

### Writing into file
Give an **Absolute Path** to the file you want to create and add output into.

- `>` : Overwrites  previous contents every time the block of code gets executed..
- `>>` : Append every new line to the already existing file.

---

## Cron Jobs
Cron schedules scripts to run automatically at fixed times.

### Commands
- crontab -e   # edit jobs
- crontab -l   # list jobs

```
* * * * *
│ │ │ │ │
│ │ │ │ └─ day of week
│ │ │ │ └── month
│ │ │ └──── day
│ │ └────── hour
└────────── minute
```

---