dnl Process this file with autoconf to produce a configure script.
AC_PREREQ(2.69)
AC_INIT([sparometer], [0.0.8], [chlor@schou.dk], [sparometer], [http://schou.dk/linux/sparometer/])
AC_CONFIG_SRCDIR([sparometer.c])
AM_INIT_AUTOMAKE
AM_CONFIG_HEADER(config.h)
CFLAGS="-Wall -pedantic -O2"
AC_SYS_POSIX_TERMIOS
AC_PROG_CC
AC_STDC_HEADERS
AC_C_CONST

AC_TYPE_SIZE_T
AC_TYPE_SSIZE_T
AC_FUNC_MALLOC
AC_FUNC_SELECT_ARGTYPES
AC_FUNC_STRFTIME
AC_HEADER_TIME
AC_PROG_GCC_TRADITIONAL
AC_STRUCT_TM

AC_CHECK_HEADERS([stdio.h])
AC_CHECK_HEADERS([stdlib.h])
AC_CHECK_HEADERS([ctype.h])
AC_CHECK_HEADERS([fcntl.h])
AC_CHECK_HEADERS([sys/ioctl.h])
AC_CHECK_HEADERS([termios.h])
AC_CHECK_HEADERS([errno.h])
AC_CHECK_HEADERS([string.h])
AC_CHECK_HEADERS([unistd.h])
AC_CHECK_HEADERS([time.h])
AC_CHECK_HEADERS([sys/select.h])
AC_CHECK_HEADERS([sys/time.h])
AC_CHECK_HEADERS([sys/types.h])
AC_CHECK_HEADERS([getopt.h])

AC_CHECK_FUNCS([memset])
AC_CHECK_FUNCS([select])
AC_CHECK_FUNCS([gettimeofday])
AC_CHECK_FUNCS([strerror])

AC_DEFINE_UNQUOTED([ISODATE], "$(date +%F)", [Date when configure was done])
AC_DEFINE_UNQUOTED([YEAR], "$(date +%Y)", [Year when configure was done])
AC_DEFINE_UNQUOTED([KERNEL_NAME], "$(uname -s)", [Compiled for operating system])
AC_DEFINE_UNQUOTED([MACHINE], "$(uname -m)", [Machine architecture])

AC_ARG_ENABLE(
	[debug],
	AS_HELP_STRING(
		[--enable-debug],
		[Enable early debug (developer)]
		),
	AC_DEFINE(
		[DEBUG],
		[1],
		[Yes debug]
		),
	AC_DEFINE(
		[DEBUG],
		[0],
		[No debug]
		)
)

SERIAL_DEFAULT=/dev/ttyUSB0
AC_ARG_ENABLE(
	[serial_device],
	AS_HELP_STRING(
		[--enable-serial-device=/dev/ttyUSB0],
		[Default serial device when none specified on command line. For FreeBSD use /dev/cuaU0. For Solaris use /dev/cua/0]
		),
	AC_DEFINE_UNQUOTED(
		[SDEVICE], 
		["$enableval"], 
		[Default serial device B]
		),
	AC_DEFINE_UNQUOTED(
		[SDEVICE], 
		"$SERIAL_DEFAULT", 
		[Default serial device C]
		)
)

AC_OUTPUT(Makefile)
