# configure.ac
AC_INIT([project1], [1.0], [your_email@example.com]) #Initializes the project with the project name, version, and contact email.
AC_PREREQ([2.69]) #Specifies the required version of autoconf.
AC_CONFIG_SRCDIR([src/main.c]) #Defines the file to verify that the source directory exists.
AC_CONFIG_HEADERS([config.h]) #Generates a config.h file if necessary.
AM_INIT_AUTOMAKE([foreign -Wall -Werror]) #Initializes Automake. The foreign option makes it less strict about GNU standards.

# Checks for a C compiler.
AC_PROG_CC

dln It is used to check for the presence of libraries and their dependencies, and to retrieve necessary compiler and linker flags to include those libraries in your project.
#PKG_CHECK_MODULES(VARIABLE-PREFIX, [MODULES], [ACTION-IF-FOUND], [ACTION-IF-NOT-FOUND])
# Check for the required libraries with pkg-config
PKG_CHECK_MODULES([MY_LIB], [gtk+-3.0 >= 3.12.0 gmodule-2.0],
                  [AC_MSG_NOTICE([GTK+ found])],
                  [AC_MSG_ERROR([GTK+ not found])])


AC_CONFIG_FILES([Makefile src/Makefile]) #Specifies the Makefiles to generate.
AC_OUTPUT #Outputs the configure script.
