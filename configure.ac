#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.71])
AC_INIT([enkidu],[1.0],[daniel.ortiz@ub.edu])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([foreign subdir-objects])
AM_PATH_PYTHON([3])

# Checks for programs.
AC_PATH_PROGS(PYTHON, python)
AC_PATH_PROGS(RSCRIPT, Rscript)

# BASH may already be set in the shell, if the admin then changes the
# the /bin/sh symlink to a non-bash shell, then the installation will
# break
unset BASH
AC_PATH_PROGS(BASH, bash, "no", [$PATH:/bin:/usr/bin:/usr/sbin])
if test x$BASH = "xno"; then
    AC_MSG_ERROR([bash is required])
fi

# Adds an extra argument to configure (enable use of DeBasher)
AC_MSG_CHECKING(whether to enable debasher library)
AC_ARG_WITH([debasher],
 [AS_HELP_STRING([--with-debasher=DIR],
   [installs the package with the necessary code to combine it with the debasher library, where DIR is the debasher home directory (containing bin/ and lib/debasher/) @<:@default=no@:>@])],
 [with_debasher=$withval],
 [with_debasher=""])
if test "$with_debasher" = ""; then
 enable_debasher_lib="no"
 AC_MSG_RESULT(no)
else
 enable_debasher_lib="yes"
 AC_MSG_RESULT(yes)
fi
AC_SUBST(DEBASHER_HOME_DIR,$with_debasher)

AC_CONFIG_FILES([Makefile m4/Makefile utils/Makefile doc/Makefile data/Makefile data/debasher_programs/Makefile])
AC_OUTPUT
