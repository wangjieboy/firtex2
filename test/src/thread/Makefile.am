AM_CPPFLAGS = -I $(top_srcdir)/include\
	-I $(top_srcdir)/extension/include\
	-I $(top_srcdir)/test/cppunit/include\
	-I $(top_srcdir)/test/src

check_PROGRAMS  = thread_test

thread_test_SOURCES = \
	ThreadTestCase.cpp\
	ThreadPoolTestCase.cpp

EXTRA_DIST = \
	ThreadTestCase.h\
	ThreadPoolTestCase.h


thread_test_LDADD= \
	$(top_builddir)/src/libfirtex.la\
	$(top_builddir)/test/src/libfirtextest_main.la\
	$(top_builddir)/test/cppunit/libcppunit.la\
	 -lpthread -ldl

thread_test_LDFLAGS = $(LIBADD_DL)

if WITH_TCMALLOC
thread_test_LDADD += -llibtcmalloc
endif


TESTS_ENVIRONMENT=LD_LIBRARY_PATH=/usr/local/lib:/usr/local/lib64 \
	HEAPCHECK=normal

TESTS = $(check_PROGRAMS)





