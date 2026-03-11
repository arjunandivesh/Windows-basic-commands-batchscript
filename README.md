# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
```
mkdir my-folder
```

<img width="377" height="39" alt="image" src="https://github.com/user-attachments/assets/d8357328-9d17-470e-a238-eefcd4f2355e" />

Remove the directory "my-folder"

## COMMAND AND OUTPUT
```
rmdir my-folder
```


<img width="408" height="50" alt="image" src="https://github.com/user-attachments/assets/dda64167-f806-4fc3-839d-039880842c94" />


Create the file Rose.txt

## COMMAND AND OUTPUT
```
type nul > Rose.txt
```

<img width="439" height="55" alt="image" src="https://github.com/user-attachments/assets/ab5b51d7-952b-42b3-8ab2-251bb7a0790c" />

Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
```
echo Hello World > hello.txt
```

<img width="558" height="52" alt="image" src="https://github.com/user-attachments/assets/586de26b-526d-48b6-9383-4676ebf34dba" />

Copy the file hello.txt into the file hello1.txt


## COMMAND AND OUTPUT
```

copy hello.txt hello1.txt
```

<img width="497" height="69" alt="image" src="https://github.com/user-attachments/assets/91616848-36a6-45bb-ab77-40c8db805ee5" />

Remove the file hello1.txt

## COMMAND AND OUTPUT
```

del hello1.txt
```

<img width="390" height="49" alt="image" src="https://github.com/user-attachments/assets/90c83ffe-04d2-417a-8a8f-f7e57e744713" />

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
```
dir hello1.txt
```

<img width="625" height="880" alt="image" src="https://github.com/user-attachments/assets/ffd94315-2487-423f-bbc8-d13219bc7fdb" />

List out all the associated file extensions 

## COMMAND AND OUTPUT
```

assoc
```

<img width="625" height="880" alt="image" src="https://github.com/user-attachments/assets/78ec6aa6-78c1-4cc3-972c-bcb7ecb9913d" />

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
```
fc hello.txt Rose.txt
```

<img width="536" height="159" alt="image" src="https://github.com/user-attachments/assets/c8231521-bffd-49d3-8d78-65ee2e732345" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".





## OUTPUT

<img width="494" height="77" alt="image" src="https://github.com/user-attachments/assets/0ef515f0-e058-4a0c-a261-77e0338a3b18" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
## CODE:
```
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE
:END
echo Thank you!
pause
```


## OUTPUT



<img width="656" height="202" alt="image" src="https://github.com/user-attachments/assets/6242154e-84ed-42bc-bf94-9a149e426c44" />


Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

## CODE:
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```


## OUTPUT

<img width="457" height="165" alt="image" src="https://github.com/user-attachments/assets/3097a69f-f690-4323-8bef-f13f5f1b71ea" />



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
##CODE:
```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```
## OUTPUT
<img width="422" height="52" alt="image" src="https://github.com/user-attachments/assets/5f7156e3-1950-430f-a167-0681b532c68c" />


Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
##CODE:
```
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU
:EXIT
echo Goodbye!
pause
exit
```

## OUTPUT 1:
<img width="410" height="192" alt="image" src="https://github.com/user-attachments/assets/bb6696bc-2b33-476b-a82f-302acaad872c" />


## OUTPUT 2:
<img width="441" height="203" alt="image" src="https://github.com/user-attachments/assets/9a31d7dc-8472-4fba-8917-5ee2e834ac83" />


## OUTPUT 3:


<img width="431" height="197" alt="image" src="https://github.com/user-attachments/assets/26cedb08-bbb4-4056-922b-595275225a10" />





# RESULT:
The commands/batch files are executed successfully.

