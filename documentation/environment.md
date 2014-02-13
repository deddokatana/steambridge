# Windows

You'll need a Windows setup with Visual Studio installed.  I'm using
2010 Express on Windows 7 64-bit.  Other modern versions of Visual Studio
and Windows are probably fine.

Visual Studio 2010 is the latest and recommend Windows compiler. [See this
document](https://developer.valvesoftware.com/wiki/Compiler_Choices).
However, this isn't a requirement.  The Windows code doesn't directly
depend on any part of the Source 1 SDK.  If you do use 2010, make sure
you install Service Pack 1.

Unfortunately, recent Visual Studio releases doesn't work inside of Wine.
There's also enough fuzziness to C++ that it's unlikely MinGW will work
without considerable persuasion.  [A good reference to the differences in
thiscall](http://www.ownedcore.com/forums/world-of-warcraft/world-of-warcraft-bots-programs/wow-memory-editing/281008-gcc-thiscall-calling-convention-linux-win32-mingw.html).
The Free Software dream of a Windows-less future remains onhold.

# Linux

You'll need an x86 Linux environment that can produce 32-bit binaries.
My test bed is a 13.10 64-bit Ubuntu install.

On a 64-bit Ubuntu installation, you'll (roughly) want *build-essential*,
*g++*, *g++-multilib*, *wine1.7*, *wine1.7-dev*, *libconfig9:i386*,
*libconfig9-dev*.  32-bit distros won't need *g++-multilib*, and
can substitute *libconfig9* for *libconfig9:i386*.  Other distros will
probably have similar requirements.

Note that libconfig9:i386 doesn't setup the *libconfig.so* library
symlink.  **cd /usr/lib/i386-linux-gnu/ ; sudo ln -s libconfig.so.9
libconfig.so** does the trick on my test machine.
