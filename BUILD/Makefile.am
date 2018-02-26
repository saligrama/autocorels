AUTOMAKE_OPTIONS = foreign
MAJOR_VERSION=1
MINOR_VERSION=0
VERSION=$(MAJOR_VERSION).$(MINOR_VERSION)
LIBTOOL_VERSION=$(MAJOR_VERSION):$(MINOR_VERSION)

ACLOCAL_AMFLAGS= -I m4
AM_CPPFLAGS = -DGMP -Wall -I. -I/usr/local/include -I/opt/local/include $(INCLUDES)
AM_LDFLAGS = -L/opt/local/lib -L/usr/local/lib -lgsl -lgmp -lm -lc

# Support both static and dynamic builds
bin_PROGRAMS = corels
include_HEADERS = rule.h

# Dynamic build
corels_SOURCES = run.cc run.hh
corels_LDADD = libcorels.la

lib_LTLIBRARIES = libcorels.la
libcorels_la_SOURCES = rulelib.c corels.cc
libcorels_la_LDFLAGS = -version-info $(LIBTOOL_VERSION)
