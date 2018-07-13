## PWNABLE.KR - FD Walkthrough

Did not have a lot of time to study for the OSCP today so I decided to check out pwnable.kr briefly. PWNABLE is a CTFlike site with a good amount of beginner, intermediate and elite challenges.  
<img src="/assets/images/pwnable.png" class="align-center" alt="">  

Not to sure what I have got myself into so I will start with the easiest. A challenge named fd.  
A popup box appears with a message and a `ssh` command.  
 `ssh fd@pwnable.kr -p2222 (pw:guest)`  

 <img src"/assets/images/pwnable-fd1.png" class="align-center" alt="">

 Connecting to the site and supplying the `guest` password I am granted access.  
 Quick `ls -aihl` and we see there are some files already in the directory as well as a file named `flag`. Try to read the file and we get Permission denied. Got to try, right?  
 There is a file named `fd.c` and what looks like the compiled binary `fd`. To view the source for `fd.c` we can run `cat fd.c` and the source code will be displayed on the screen.
 
