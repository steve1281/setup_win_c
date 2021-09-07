# C/C++ lets do hello world

Setting up and testing C/C++ on a new Windows 10 environment, and using them in visual code.


[reference link](https://code.visualstudio.com/docs/languages/cpp)

## Check for existing

```
C:\Users\steve\projects\simple_c>g++
'g++' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\steve\projects\simple_c>clang --version
'clang' is not recognized as an internal or external command,
operable program or batch file.

```

So, not installed.

## Install mingw

Get the [installer](https://github.com/msys2/msys2-installer/releases/download/2021-06-04/msys2-x86_64-20210604.exe)

Follow [instructions](https://www.msys2.org/)

Eventually:

```
$ gcc --version
gcc.exe (Rev5, Built by MSYS2 project) 10.3.0
Copyright (C) 2020 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.


steve@SteveRazer MINGW64 ~
$
```

## Get this working in visual code

### PATH

1. In the Windows search bar, type 'settings' to open your Windows Settings.
2. Search for Edit environment variables for your account.
3. Choose the Path variable and then select Edit.
4. Select New and add the Mingw-w64 destination folder path, with \mingw64\bin appended, to the system path. The exact path depends on which version of Mingw-w64 you have installed and where you installed it. If you used the settings above to install Mingw-w64, then add this to the path: C:\msys64\mingw64\bin.
5. Select OK to save the updated PATH. You will need to reopen any console windows for the new PATH location to be available.

Open a new cmd window.

Launch code.

Open a terminal, and check:

```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\steve\projects\simple_c> g++ --version
g++.exe (Rev5, Built by MSYS2 project) 10.3.0
Copyright (C) 2020 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.  There is NO 
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

PS C:\Users\steve\projects\simple_c>
```

```
PS C:\Users\steve\projects\simple_c> gdb --version
GNU gdb (GDB) 10.2
Copyright (C) 2021 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
PS C:\Users\steve\projects\simple_c>
```

Add some files:

main.c

```
#include <stdio.h>

void main()
{
    printf("Hello World!\n");
}
```

and main.cpp

```
#include <iostream>
using namespace std;

int main()
{
    cout << "hello world" << endl;
   
}

```

From both of these, use Terminal - Run/Build Task

Pick the gcc or g++ (for C or C++ respectively)

## The good news

This is all one time setup, since C/C++ doesn't use virtual environments like python.  

# More extensive tests

## console tetris (console_tetris.cpp)

This is a just an implementation of `javidx9`'s tetris: [Code-It-Yourself! Tetris - Programming from Scratch (Quick and Simple C++)](https://www.youtube.com/watch?v=8OK8_tHeCIA)

Notes:

* needs to be run from a cmd window that 80 wide. 
* needs to have the unicode activated

## more to come...


