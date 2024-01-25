## CSE 15L Lab Report 1

## Command: `cd`

## Example using `cd` with no arguments


<img width="386" alt="Screenshot 2024-01-25 at 11 12 46 AM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/7d2bba3f-16a5-4e89-944a-8f7ebe6b474f">

When the command was run, the working directory was the home directory as indicated by the `~` symbol with nothing following. Since I ran it with no arguments, there is nothing after the `cd` in the command line. The `cd` command changes directories, but since there was no argument, the directory did not change and I remained in the home directory. This is not an error as I did not provide any arguments, so I remained in the same directory as when the command was run.

## Example using `cd` with a path to a directory as an argument
<img width="408" alt="Screenshot 2024-01-25 at 11 14 29 AM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/71e82c7d-a2a3-4a99-8658-10e358af289d">

When the command was run, the working directory was the home directory as indicated by the `~` symbol with nothing following. The argument I used was the `lecture1` directory. Since I used the `cd` command to change directories, after running the command I changed directories into the `lecture1` directory, as indicated by the text following the `~` symbol in the second line. This is not an error as the expected outcome of the `cd` command is to change directories into the one used as an argument.


##  Example using `cd` with a path to a file as an argument

<img width="559" alt="Screenshot 2024-01-25 at 3 31 33 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/a22c0d17-4f19-49b9-8e68-89b0156854f6">


When the command was run, the working directory I had was the `lecture1` directory, as indicated with the text after the `~` symbol. My output after running the command with the path to text file `es-mx.txt` was a message saying the argument is not a directory. This is an error, as the command is expecting a directory as an argument so it can change directories, however the argument I provided was a path to a file, which is not a directory that can be changed to.


## Command: `ls` 

## Example using `ls` with no arguments

<img width="503" alt="Screenshot 2024-01-24 at 10 15 50 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/cd3fdc7d-f190-411d-a4b6-2af1d437a5c5">

When this command was run, the working directory was the home directory as indicated by the `~` symbol with nothing following. The command `ls` lists all contents under the current directory. Since I ran the command with no arguments, it listed all contents under the home directory, which was only `lecture1`. This is not an error, as this is the expected output of this command when no argument is given. 

## Example using `ls` with a path to a directory as an argument

<img width="430" alt="Screenshot 2024-01-24 at 10 16 59 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/6f7a8ad8-f355-404b-9e6a-2ec5f6ee4876">

When this command was run, the working directory was the home directory as indicated by the `~` symbol with nothing following.The command `ls` lists all contents under the current directory or directory given in the argument. Since I ran the command with the argument being the `lecture1` directory, it listed all of the contents under the `lecture1` directory which included `Hello.class`, `Hello.java`, `messages`, and `README`. This is not an error as this is the expected output of this command with `lecture1` as an argument.

##  Example using `ls` with a path to a file as an argument

<img width="561" alt="Screenshot 2024-01-25 at 3 38 12 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/28277238-b792-4adc-9b9d-f069759ecdd9">

When the command was run, the working directory I had was the `lecture1` directory, as indicated with the text after the `~` symbol.The command `ls` lists all contents under the current directory or directory given in the argument, however since the argument I provided was a pathway to a file, it repeats the pathway, indicating that `en-us.txt` exists under the messages directory. This is not an error, as the file `en-us.txt` exists in the `messages` directory.


## Command: `cat`

## Example using `cat` with no arguments

<img width="396" alt="Screenshot 2024-01-24 at 10 25 14 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/e10ce0f5-595a-4934-8de5-216d704cea49">

When this command was run, the working directory was the home directory as indicated by the `~` symbol with nothing following. The command `cat` concatenates the contents of files together. Since I ran the command with no arguments, nothing is being concatenated, so the result is nothing being printed as the output. This is not an error, as I did not run the command with any arguments, so nothing being printed is the expected output.


## Example using `cat` with a path to a directory as an argument

<img width="333" alt="Screenshot 2024-01-25 at 3 16 27 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/e3b7f555-3eee-4713-bda6-ef9b615ddb22">


When this command was run, the working directory was the home directory as indicated by the `~` symbol with nothing following. The command `cat` concatenates the contents of files together. When run with a path to a directory as an argument, the output is a mesage stating that `lecture1`, which was the argument, is a directory. This is an error message because the argument is not meant to be a directory for the command to function, as `cat` is meant for files. 


##  Example using `cat` with a path to a file as an argument
<img width="478" alt="Screenshot 2024-01-25 at 3 25 34 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/dc03c722-604d-4773-b814-f303f03a0c68">


<img width="689" alt="Screenshot 2024-01-24 at 10 28 00 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/b436a9cb-26c6-4726-80c9-70a5c5a9f752">

When this command was run, the working directory was the `lecture1`. For the first screenshot, the argument was a path to a file and the second, the arguments were two paths to different files. The command `cat` concatenates the contents of the files together, so when one path to a file is given as an argument, it outputs the contents of the one file concatenated with nothing, as there is no other argument. When two arguments are provided, as shown, the output is the contents of both of the files printed. This is not an error, as this is the expected output of the command `cat` being used.

