## PWNABLE.KR - FD Walkthrough
<img src="/assets/images/pwnable-fd.png" class="align-left" />

Did not have a lot of time to study for the OSCP today so I decided to check out pwnable.kr briefly. PWNABLE is a CTFlike site with a good amount of beginner, intermediate and elite challenges.  
<img src="/assets/images/pwnable.png" class="align-center" alt="">  

Not to sure what I have got myself into so I will start with the easiest. A challenge named fd.  
A popup box appears with a message and a `ssh` command.  
 <img src="/assets/images/pwnable-fd1.png" />  

 Connecting to the site and supplying the `guest` password I am granted access.  
 <img src="/assets/images/pwnable-fd2.png" />
 Quick `ls -aihl` and we see there are some files already in the directory as well as a file named `flag`. Try to read the file and we get Permission denied. Got to try, right?  
 There is a file named `fd.c` and what looks like the compiled binary `fd`. To view the source for `fd.c` we can run `cat fd.c` and the source code will be displayed on the screen.  
 <img src="/assets/images/pwnable-fd4.png" />  

 Looking at the source code tells us that the the binary `fd` accepts an argument. We see this in the `main` function parameters `(int argc, char* argv[], char* envp[])`.
 So what do we need to supply the binary then? On line 10 we see that the supplied argument is subtracted by a hex value of `0x1234` and then the `flag` file is read inside a if statement. So what is hex `0x1234`? We can use python to find out.
<img src="/assets/images/pwnable-fd5.png" />  
So the hex value of `0x1234` is `4660` and now lets see what happens when we supply this value as an argument.  
`$ ./fd 4660`  
Nothing is happening and the cursor is dropped to a new line. Reviewing the if statement in the source code it would appear we need to enter `LETMEWIN` hit enter.
The binary accepts the input and we are presented with our flag. Awesome!
<img src="/assets/images/pwnable-fd6.png" />  
Our flag is `mommy! I think I know what a file descriptor is!!`
