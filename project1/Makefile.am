# Makefile.am in the root directory
AUTOMAKE_OPTIONS = foreign #Loosens strict GNU rules, making it less strict about project structure.
SUBDIRS = src #Specifies the subdirectories to descend into during the build process. In this case, it tells make to look inside the src directory and process its Makefile.

clean-local:
	@rm config.status configure config.log
	@rm Makefile
	@rm -r autom4te.cache/
	@rm aclocal.m4
	@rm compile install-sh missing Makefile.in
