## Icon to .exe

This repository is a example of adding a icon to an .exe program, is base on the following anwser in [stackoverflow](https://stackoverflow.com/questions/31412460/c-adding-icon-to-exe-using-makefile-windows) and is based using [gcc](https://gcc.gnu.org/) instead of [MSVC](https://www.microsoft.com/en-us/download/details.aspx?id=5555)


First we need a .ico with support for more than one layer,with sizes, 128x128, 64x64, 32x32 and 16x16,

I created the ico using [gimp](https://www.gimp.org/downloads/)

Then, we need a program call windres, which compiles [windows resource files](https://msdn.microsoft.com/en-us/library/cc194804.aspx), and we add to **resource.rc** the following `MAINICON ICON "xterm.ico"`.

Then we may build the resource file using [windres](https://www.cygwin.com/cygwin-ug-net/windres.html)

`$ windres resource.rc resource.o`

Then, we just need to add the **resource.o** to the compiler.

`$ gcc -o main.exe main.c resource.o `
