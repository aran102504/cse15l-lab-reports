# CSE 15l Lab Report 2
## Part 1:
## My Chat Server Code:
<img width="894" alt="Screenshot 2024-01-29 at 10 38 25 PM 1" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/3ff3d89b-39b1-49da-b38f-e2c4307bb7bc">

## Example 1 using `/add-message`

http://localhost:4000/add-message?s=Hello&user=angela
<img width="1210" alt="Screenshot 2024-01-29 at 10 53 09 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/984f01af-9d01-4d6e-b34c-80d0581af112">

In this example, the handler method is called, as the number of arguments in the command line was not equal to zero. The `url` is `http://localhost:4000/add-message?s=Hello&user=angela`, the String `user` is `"angela"`, and the String `message` is `Hello`. The value of list when this method is called is `"" `,  but after it becomes `angela: Hello`, which is what can be seen printed in the screenshot above. The value of `list ` changes with this request, as list concatenates and stores a new message from a user based on the arguments everytime the method is called. The value of the strings `user` and `message` both change as well, as they are both empty strings before the method is called and then change according to the corresponding argument, in this case, the strings `"angela"` and `"Hello"`, respectively.


## Example 2 using `/add-message`

http://localhost:4000/add-message?s=How%20are%20you&user=jpolitz
<img width="536" alt="Screenshot 2024-01-29 at 10 57 02 PM" src="https://github.com/aran102504/cse15l-lab-reports/assets/157055098/4f404e28-2f09-4708-aaf4-129e495dd025">

In this example, the handler method is called, as the number of arguments in the command line was not equal to zero. The `url` is `http://localhost:4000/add-message?s=How%20are%20you&user=jpolitz`, the String `user` is `"jpolitz"`, and the String `message` is `"How are you"`. The value of list when this method is called is `angela: Hello`, but after it is called, `"jpolitz: How are you"` is concatenated with a new line, which is what can be seen printed in the screenshot above. The value of `list ` changes with this request, as list concatenates and stores a new message from a user based on the arguments everytime the method is called. The value of the strings `user` and `message` both change as well, as they are both empty strings before the method is called and then change according to the corresponding argument, in this case, the strings `"jpolitz"` and `"How are you"`, respectively.

## Part 2:



## Part 3:
In Week 3 lab, something new I learned were the commands `scp` and `mkdir`. After looking their functions up on Google because the instructions for the lab said to, I learned that the `scp` command allows for the secure copy of files and directories between either the remote host and the local host, or two remote hosts. When looking up the `mkdir` command, I learned that `mkdir` stands fore "make directory". Using this command in the command line, users can create a new directory, subdirectory, or multiple directories at once. These are both commands I have never seen before.
