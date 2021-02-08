# labscc
Linux-Android-Mac-BSD System Call Compatibility.  

Making systems play nice with portable system calls.

What?
This will be an effort to create a package of "portable" system calls that will be usable on all unix like systems and a base for new operating systems to build on.
It can be seen as an alternative to POSIX/UNIX standards and will attempt to work as a backend to bridge system call handling between systems.  

Why?
In it's current state there are multiple standards (think Unix/POSIX) that can be met but do not include ABI compatibility.  You cannot simply take a program built for Linux, MacOS, BSD or android and run it on a secondary system.  This creates rifts in the development and maintenance of applications and components.  Slowing overall development.

If we can create a set of system calls that can be installed on any open source (and possibly closed source) OS this will allow developers for applications, drivers, etc. to spend their time working on advancing their projects rather than on porting code to work on another OS.

How?
TBD but my current vision on how to go about this is to catch calls for non-present system calls, determine the OS the system call is intended for, adjust the input to the system call to match what the host OS expects before passing it to the proper system call.  Any returned data will be properly adjusted and returned to the calling program.

Foreseen issues?
1. The speed at which this conversion can be completed may cause slight delays.
2. The ability to get support behind a new standard.
3. The sheer number of system calls that must be taken into account.
