# unpv1.3e

QUICK AND DIRTY
===============

Execute the following from the src/ directory:

    ./configure    # try to figure out all implementation differences

    cd lib         # build the basic library that all programs need
    make           # use "gmake" everywhere on BSD/OS systems

    cd ../libfree  # continue building the basic library
    make

    cd ../libroute # only if your system supports 4.4BSD style routing sockets
    make           # only if your system supports 4.4BSD style routing sockets

    cd ../libxti   # only if your system supports XTI
    make           # only if your system supports XTI

    cd ../intro    # build and test a basic client program
    make daytimetcpcli
    ./daytimetcpcli 127.0.0.1

If all that works, you're all set to start compiling individual programs.

Notice that all the source code assumes tabs every 4 columns, not 8.

MORE DETAILS
============

5.  If you need to make any changes to the "unp.h" header, notice that it
    is a hard link in each directory, so you only need to change it once.

6.  Go into the "lib/" directory and type "make".  This builds the library
    "libunp.a" that is required by almost all of the programs.  There may
    be compiler warnings (see NOTES below).  This step is where you'll find
    all of your system's dependencies, and you must just update your cf/
    files from step 1, rerun "config" and do this step again.

6.  Go into the "libfree/" directory and type "make".  This adds to the
    "libunp.a" library.  The files in this directory do not #include
    the "unp.h" header, as people may want to use these functions
    independent of the book's examples.

8.  Once the library is made from steps 5 and 6, you can then go into any
    of the source code directories and make whatever program you are
    interested in.  Note that the horizontal rules at the beginning and
    end of each program listing in the book contain the directory name and
    filename.

