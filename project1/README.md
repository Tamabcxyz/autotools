# Project 1
```
mkdir project1
cd project1
mkdir src

```
```
touch src/main.c
/* src/main.c */
#include <stdio.h>

int main() {
    printf("Hello, Autotools!\n");
    return 0;
}
```
```
touch configure.ac
# configure.ac
AC_INIT([project1], [1.0], [your_email@example.com])
AC_PREREQ([2.69])
AC_CONFIG_SRCDIR([src/main.c])
AC_CONFIG_HEADERS([config.h])
AM_INIT_AUTOMAKE([foreign -Wall -Werror])

# Checks for programs.
AC_PROG_CC

# Create output files
AC_CONFIG_FILES([Makefile src/Makefile])
AC_OUTPUT

```
```
touch Makefile.am
# Makefile.am in the root directory
AUTOMAKE_OPTIONS = foreign
SUBDIRS = src
```
```
touch src/Makefile.am
# src/Makefile.am
bin_PROGRAMS = project1
myproject_SOURCES = main.c
```
```
aclocal # Generates aclocal.m4
autoconf # Generates configure script
automake --add-missing  # Generates Makefile.in and missing auxiliary files

OR

autoreconf -i
```
```
./configure
make
sudo make install

OR You can also specify a different installation path by running:

./configure --prefix=/your/custom/path
make
sudo make install
```
```
Make distribution for your project
make dist (it will create project1-1.0.tar.gz)
tar -xvzf project1-1.0.tar.gz
./configure
make
./test/src/project1
make distclean (remove all file unnessesary)
```
####
Libtool: Handling libraries             
• Initialize libtool: Add "LT_INIT" to configure.ac     
• Sample Makefile.am (should also make .pc file):       
ACLOCAL AMFLAGS = -I m4-install         
lib_LTLIBRARIES = libwhine-1.0.la #In lib, install library           
libwhine 10 la SOURCES = src/whine.c src/whine.h            
libwhine 10 la LDFLAGS = -version-info 0:0:0        
include_HEADERS = src/whine.h #In include, install header           
bin_PROGRAMS = hello            
hello_SOURCES = src/hello.c         
hello_LDADD = $(lib_LTLIBRARIES) #Program uses library 25           