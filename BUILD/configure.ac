#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([FULL-PACKAGE-NAME], [VERSION], [BUG-REPORT-ADDRESS])
AC_CONFIG_SRCDIR([src/pmap.cc])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([Makefile])

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC

# Checks for libraries.

AC_CHECK_LIB([gmp], [__gmpz_clear], [], [
	echo "GMP (Gnu multiprecision) library is required for this program"
	exit -1])
AC_CHECK_LIB([m],[floor])
AC_CHECK_LIB([gslcblas],[cblas_dgemm])
AC_CHECK_LIB([gsl], [gsl_ran_poisson], [], [
	echo "GSL library is required for this program"
	exit -1])

# Checks for header files.
AC_CHECK_HEADERS([stdlib.h gmp.h string.h sys/time.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_C_INLINE
AC_TYPE_SIZE_T

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_REALLOC
AC_CHECK_FUNCS([gettimeofday memmove memset select strchr strdup strrchr strstr uname])

AC_OUTPUT
