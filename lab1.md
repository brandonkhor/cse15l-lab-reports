# Lab Report 1

## `cd` section

Using `cd` with no arguments did nothing when in the `/home` directory

![Image](ss1.png)

Working Directory: '/home'

However, when using `cd` with no arguments in the `/home/lecture1/messages`, it brings the user back to the `/home` directory

![Image](ss10.png)

Working directory: `/home/lecture1/messages`

---

Using `cd` with a directory as an argument changed the directory to the one listed, in this case `lecture1`
![Image](ss2.png)

Working directory: `/home`

---

Using `cd` with a file as an argument resulted in an error, for it is not a directory. In this case, since `Hello.java` is not a directory and is a file, it throws an error at us

![Image](ss3.png)\

Working directory: `/home/lecture1`

---

## `ls` section

Using `ls` with no arguments outputs all directories and files in the current directory. In this case, all directories and files in the directory `lecture1` was outputted. Note that directories are in blue letters while files are in black.

![Image](ss4.png)

Working directory: `/home/lecture1`

---

Using `ls` with a directory as an argument outputs all directories and files in the argument (which is a directory). In this cases, all files in the `messages` directory were outputted.

![Image](ss5.png)

Working directory: `/home/lecture1`

---

Using 'ls' with a file will just output the file name.

![Image](ss6.png)

Working directory: `/home/lecture1`

---

## `cat` section

Using `cat` with no arguments won't ouput anything, but prompt the user for an input. If the user inputs a string, it will output the same string back to the user. Note that no error is outputted and `cat` can be exited using Ctrl + D.

![Image](ss7.png)

Working directory: `/home/lecture1`

---

Using `cat` with a directory as an argument will produce an error, for it is a directory and not a file. Since `cat` prints the contents of a file, it will not work with a directory.

![Image](ss8.png)

Working directory: `/home/lecture1`

---

Using `cat` with a file as an argument prints the contents of the file

![Image](ss9.png)

Working directory: `/home/lecture1`

---
