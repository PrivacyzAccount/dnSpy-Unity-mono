INCLUDES = $(GLIB_CFLAGS) -I$(top_srcdir)

if PLATFORM_WIN32
export HOST_CC
endif

if JIT_SUPPORTED
runtime_lib=../mini/libmono.la
else
runtime_lib=../interpreter/libmint.la
endif

if CROSS_COMPILING
bin_PROGRAMS = 
else
bin_PROGRAMS = monodis
endif

noinst_LIBRARIES = libmonodis.a

libmonodis_a_SOURCES =	\
	get.c		\
	get.h		\
	dis-cil.c	\
	dis-cil.h	\
	util.c		\
	util.h

monodis_SOURCES =	\
	dump.c		\
	dump.h		\
	main.c		\
	meta.h		\
	declsec.c	\
	declsec.h

monodis_LDADD = 			\
	libmonodis.a			\
	$(runtime_lib)			\
	$(GLIB_LIBS) 

man_MANS = monodis.1

EXTRA_DIST = $(man_MANS)
