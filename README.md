#README for libsocket

##USE

It's recommended to compile libsocket statically into your program (by placing the .c and .h files in your source tree).
You don't have to mind legal issues because libsocket is licensed by a slightly modified BSD license which permits
any use, as long as you include the license text in your product (so it's clear that libsocket is licensed by this License)
and the notice that *we* wrote libsocket (as described in the license)
It's friendly to mention libsocket in your product's Readme or ads anyway, of course :)
libsocket is built for little programs whose author(s) are too lazy to build own algorithms and functions for socket (UNIX (coming soon)
and Internet Domain (TCP/UDP)) communication.

As you should know as experienced C programmer, it's quite easy to use this library.
Simply add the line into the source files where the library is used:

	# include "path/to/lib{inet,unix}socket.h"

and call the compiler (eventually in a makefile) with the name of the C file:

	$ gcc lib{inet,unix}socket.c ownfile1.c ownfile2.c
	# or
	$ gcc -c libsocket.c
	$ gcc ownfile1.c ownfile2.c libsocket.o
	# etc. pp.

##FEATURES AND ADVANTAGES

The libsocket library supports following things and protocols:

* IPv4 (client)
* IPv6 (client, if your machine supports it)
* TCP (client)
* UDP (client)
* UNIX Domain Sockets (by now only as client)
* Intelligent algorithms to get the best connection and no errors
* Easy use (one function call to get a socket up and running, one another to close it)
* Proper error processing (using errno, gai\_strerror() etc).

One of the main advantages of libsocket is that you don't have to write the often complex and error-prone
procedures for connecting a socket, check it on errors etc. yourself.

Support for server sockets will be added soon.

##PLATFORMS

I'd like to get test reports and experiences from you. I already tested the library under the following conditions:

* Linux 3.1, gcc-4.6, TCP IPv4 sockets
* Linux 3.1, gcc-4.7, TCP IPv4 sockets

It is planned to test and get libsocket working on OpenBSD 5.0. If you want, you may port it anywhere.