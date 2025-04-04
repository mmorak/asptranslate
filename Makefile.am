############################
# FLAGS:                   #
############################

# tell automake to pass certain flags to autoconf on re-run
ACLOCAL_AMFLAGS = -I m4 ${ACLOCAL_FLAGS}

# tell automake to pass certain flags to 'ctags'
AM_CTAGSFLAGS = --extra=+f

#FIXME: don't assume GCC, do feature detection in configure.ac
# tell automake to pass certain CFLAGS to the compiler
AM_CFLAGS = \
	-pedantic-errors \
	-Wpedantic \
	-Wall \
	-Wextra \
	-Wdouble-promotion \
	-Wswitch-default

# initialize variables
EXTRA_DIST =
CLEANFILES =
BUILT_SOURCES =

############################
# LIBRARIES TO BUILD:	   #
############################

############################
# PROGRAMS TO BUILD:	   #
############################

# tell automake which programs to build
bin_PROGRAMS = \
	acyc2solver \
	graph2sat \
	lp2acyc \
	lp2normal \
	lp2normal2 \
	lp2sat \
	lpreify \
	support \
	unsat2lp

#-----------------------#
# program build options #
#-----------------------#

# list all source code files for the programs

noinst_HEADERS = \
	src/args.h \
	src/common.h \
	src/implyaux.h \
	src/intarray.h \
	src/litint.h \
	src/plan.h \
	src/robdd.h \
	src/simplification.h \
	src/unarysort.h

ACYC = src/acyc.h src/acyc.c
CTR = src/counter.h src/counter.c
NORMAL = src/prime.h src/prime.c \
	src/condflags.h src/condflags.c \
	src/expression.h src/expression.c
PRIM = src/primitives.h src/primitives.c
SCC = src/scc.h src/scc.c

acyc2solver_SOURCES = $(ACYC) $(SCC) src/acyc2solver.c
graph2sat_SOURCES = src/graph2sat.c
lp2acyc_SOURCES = $(ACYC) $(SCC) src/lp2acyc.c
lp2normal_SOURCES = src/lp2normal.c
lp2normal2_SOURCES = $(NORMAL) src/lp2normal2.c
lp2sat_SOURCES = $(ACYC) $(SCC) src/lp2sat.c
lpreify_SOURCES = $(PRIM) $(SCC) src/lpreify.c
support_SOURCES = $(CTR) $(SCC) src/support.c
unsat2lp_SOURCES = src/unsat2lp.c

############################
# DISTRIBUTION OPTIONS:	   #
############################

# tell automake about scripts that should be distributed in the tarball, but
# not installed on "make install"
dist_noinst_SCRIPTS = autogen.sh

# tell automake to clean the generated files on "make clean"
CLEANFILES += $(BUILT_SOURCES)

############################
# UNIT TESTS:              #
############################

# tell automake to recursively go into the test directory
#SUBDIRS = tests
