# IO-wargame-walkthrough

<h4>Level 01<h4>
  we need to get ssh connection to the level1@io.netgarage.org.we have to give level1 password to get access to the game.the password is on the website called http://io.netgarage.org/ 
  
  
![re_1](https://user-images.githubusercontent.com/22831322/76156425-66d05b00-6120-11ea-97f4-2523f6d4e235.PNG)

after that type ls to see the files inside the current directory.it will show you readme file. Inside that file there are instructions about how to play the game.
go to the directly called levels as mentioned in the readme file. Then type ls -las level01 to get the executable file. After that you must execute the file. Then it will ask for the password. We must figure out what that password is. In order to do that we need to reverse engineer the executable file. We need to type “gdb level01” to debug the file. After that type “set disassembly-flavor intel” to covert assembly to something understandable. after that type “disass main” to dump the assembly code.in that code there is a password comparison done by the “cmp” command. Simply what this program does is comparing our password to it's hardcoded password. Since the password hardcoded, we only need to get the value of the memory address that is compared. Password is in the “0*10f” memory address. Only we need to do is to dump the value of that memory address. Type “print 0*10f” to get the value. The password is 271.after getting the password we execute the file and type the password. Then it will give us user privilege to access the “ /home/level2/.pass” directory. If we type “id” command, we can see user privileges. Type “cat /home/level2/.pass” to get the level02 password. Password is "XNWFtWKWHhaaXoKI"

![re_2](https://user-images.githubusercontent.com/22831322/76156663-887f1180-6123-11ea-9097-e7c741c578d0.PNG)


<h4>Level 02<h4>
  
we need to log in as the level1 using level 2 password. After that as previously mentioned in level01 we need to go to the directory called levels. In that directory there is a file called level02.we need to execute that file. It will say there is a source code of this program in the current directory. We need to study it. It is a source code that written using C language.

![level2](https://user-images.githubusercontent.com/22831322/76156787-42c34880-6125-11ea-9fe4-b58bf48c4546.PNG)
  
This C code integer overflow vulnerability. The only thing we need to do is to give integer values that result in integer overflow as command line arguments. I gave "-122222222222222222222222222222" and "-1". After giving these values the program will give us privileges of level03.You can check the privileges using “id” command. Like previously mentioned, we need to type “cat /home/level3/.pass” to get the password. The password for level03 is “OlhCmdZKbuzqngfz”
