# IO-wargame-walkthrough

<h4>Level 01<h4>
  we need to get ssh connection to the level1@io.netgarage.org.we have to give level1 password to get access to the game.the password is on the website called http://io.netgarage.org/ 
  
  
![re_1](https://user-images.githubusercontent.com/22831322/76156425-66d05b00-6120-11ea-97f4-2523f6d4e235.PNG)

after that type ls to see the files inside the current directory.it will show you readme file. Inside that file there are instructions about how to play the game.
go to the directly called levels as mentioned in the readme file. Then type ls -las level01 to get the executable file. After that you must execute the file. Then it will ask for the password. We must figure out what that password is. In order to do that we need to reverse engineer the executable file. We need to type “gdb level01” to debug the file. After that type “set disassembly-flavor intel” to covert assembly to something understandable. after that type “disass main” to dump the assembly code.in that code there is a password comparison done by the “cmp” command. Simply what this program does is comparing our password to it's hardcoded password. Since the password hardcoded, we only need to get the value of the memory address that is compared. Password is in the “0*10f” memory address. Only we need to do is to dump the value of that memory address. Type “print 0*10f” to get the value. The password is 271.after getting the password we execute the file and type the password. Then it will give us user privilege to access the “ /home/level2/.pass” directory. If we type “id” command, we can see user privileges. Type “cat /home/level2/.pass” to get the level02 password.
