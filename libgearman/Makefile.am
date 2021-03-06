# Gearman server and library
# Copyright (C) 2008 Brian Aker, Eric Day
# All rights reserved.
#
# Use and distribution licensed under the BSD license.  See
# the COPYING file in the parent directory for full text.

if HAVE_LIBDRIZZLE
QUEUE_LIBDRIZZLE_H= queue_libdrizzle.h
QUEUE_LIBDRIZZLE_C= queue_libdrizzle.c
endif

if HAVE_LIBMEMCACHED
QUEUE_LIBMEMCACHED_H= queue_libmemcached.h
QUEUE_LIBMEMCACHED_C= queue_libmemcached.c
endif

if HAVE_LIBSQLITE3
QUEUE_LIBSQLITE3_H= queue_libsqlite3.h
QUEUE_LIBSQLITE3_C= queue_libsqlite3.c
endif

if HAVE_LIBPQ
QUEUE_LIBPQ_H= queue_libpq.h
QUEUE_LIBPQ_C= queue_libpq.c
endif

lib_LTLIBRARIES= libgearman.la

libgearmanincludedir= ${includedir}/libgearman

dist_libgearmaninclude_HEADERS= \
	client.h \
	conf.h \
	conf_module.h \
	conn.h \
	constants.h \
	gearman.h \
	gearmand.h \
	gearmand_thread.h \
	gearmand_con.h \
	job.h \
	packet.h \
	server.h \
	server_client.h \
	server_con.h \
	server_job.h \
	server_function.h \
	server_packet.h \
	server_thread.h \
	server_worker.h \
	structs.h \
	task.h \
	visibility.h \
	worker.h \
	$(QUEUE_LIBDRIZZLE_H) \
	$(QUEUE_LIBMEMCACHED_H) \
	$(QUEUE_LIBSQLITE3_H) \
	$(QUEUE_LIBPQ_H) \
	protocol_http.h

noinst_HEADERS= \
	common.h

libgearman_la_SOURCES= \
	client.c \
	conf.c \
	conf_module.c \
	conn.c \
	gearman.c \
	gearmand.c \
	gearmand_thread.c \
	gearmand_con.c \
	job.c \
	packet.c \
	server.c \
	server_client.c \
	server_con.c \
	server_job.c \
	server_function.c \
	server_packet.c \
	server_thread.c \
	server_worker.c \
	task.c \
	worker.c \
	$(QUEUE_LIBDRIZZLE_C) \
	$(QUEUE_LIBMEMCACHED_C) \
	$(QUEUE_LIBSQLITE3_C) \
	$(QUEUE_LIBPQ_C) \
	protocol_http.c

libgearman_la_CFLAGS= ${AM_CFLAGS} -DBUILDING_LIBGEARMAN
libgearman_la_LDFLAGS= -version-info $(GEARMAN_LIBRARY_VERSION) \
	$(LD_VERSION_SCRIPT)

libgearman_la_LIBADD= \
	$(LTLIBEVENT) \
	$(LTLIBUUID) \
	$(LTLIBDRIZZLE) \
	$(LTLIBMEMCACHED) \
	$(LTLIBSQLITE3) \
	$(LTLIBPQ)

EXTRA_DIST= libgearman.ver
