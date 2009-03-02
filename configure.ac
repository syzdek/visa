#
#   Visa Single Sign-on Web System
#   Copyright (C) 2009 David M. Syzdek <syzdek@bindlebinaries.net>
#
#   @VISA_COPYRIGHT_START@
#
#   This program is free software; you can redistribute it and/or modify
#   it under the terms of the GNU General Public License as published by
#   the Free Software Foundation; either version 2 of the License, or
#   (at your option) any later version.
#
#   This program is distributed in the hope that it will be useful,
#   but WITHOUT ANY WARRANTY; without even the implied warranty of
#   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#   GNU General Public License for more details.
#
#   You should have received a copy of the GNU General Public License along
#   with this program; if not, write to the Free Software Foundation, Inc.,
#   51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.
#
#   @VISA_COPYRIGHT_END@
#
#   configure.in - automate compiling on a unix platform
#

AC_PREREQ(2.63)

AC_COPYRIGHT([Copyright (C) 2009 David M. Syzdek <syzdek@bindlebinaries.net>.])
AC_REVISION(0.0.1)
AC_INIT([Visa Single Sign-on Web System],[0.0.0],[syzdek@bindlebinaries.net],[visa])

AC_SUBST([RELEASE_MONTH],     ["February 2009"])
AC_SUBST([PACKAGE_COPYRIGHT], ["Copyright (C) 2009 David M. Syzdek <syzdek@bindlebinaries.net>."])
AC_DEFINE_UNQUOTED(PACKAGE_COPYRIGHT, ["$PACKAGE_COPYRIGHT"], ["Copyright info"])

# Version Info:
#    Current    -- the current version number of this API
#    Revision   -- the revision of the implementation of the API version
#    Age        -- How many seqential past API versions is supported by
#                  this implementation
# Format => Current:Revision:Age
AC_SUBST(LIB_VERSION_INFO, 0:0:0)
AC_SUBST(LIB_RELEASE_INFO, 0) # used by Win32 DLLs

AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_SRCDIR([visa.tags])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])

# determines host type
AC_CANONICAL_BUILD
AC_CANONICAL_HOST
AC_CANONICAL_TARGET

# configures for automake
AM_INIT_AUTOMAKE(gnu std-options subdir-objects)

# Compilers                                                       
AC_PROG_CC
AM_PROG_CC_C_O
AC_PROG_INSTALL
AC_USE_SYSTEM_EXTENSIONS # replaces AC_AIX AC_GNU_SOURCE AC_MINIX
AC_C_BIGENDIAN

# binary locations
AC_PATH_PROG([SHELL],	sh bash,	[AC_MSG_ERROR([missing "sh"])], [$PATH])
AC_CHECK_TOOLS(AR,	ar gar,		[AC_MSG_ERROR([missing binutil "ar"])])
AC_CHECK_TOOLS(LD,	ld gld,		[AC_MSG_ERROR([missing binutil "ld"])])
AC_CHECK_TOOLS(NM,	nm gnm,		[AC_MSG_ERROR([missing binutil "nm"])])
AC_CHECK_TOOLS(RANLIB,	ranlib granlib,	[AC_MSG_ERROR([missing binutil "ranlib"])])
AC_CHECK_TOOLS(STRIP,	strip gstrip,	[AC_MSG_ERROR([missing binutil "strip"])])

# shell programs
AC_PROG_AWK
AC_PROG_EGREP
AC_PROG_FGREP
AM_PROG_LEX
AC_PROG_LN_S

AC_CHECK_LIB([ibrary],[books],,[AC_MSG_NOTICE([Suggest increasing funding to purchase books.])])
AC_VISA_GIT_PACKAGE_VERSION

# GNU Libtool Support
AC_LIBTOOL_DLOPEN
AC_DISABLE_FAST_INSTALL
AC_LIBTOOL_WIN32_DLL
AC_PROG_LIBTOOL

# Creates outputs
AC_CONFIG_FILES([Makefile])
AC_OUTPUT

# Show local config
AC_MSG_NOTICE([ ])
AC_MSG_NOTICE([   Please send suggestions to:   $PACKAGE_BUGREPORT])
AC_MSG_NOTICE([ ])
AC_MSG_NOTICE([   run 'make all'])
AC_MSG_NOTICE([ ])

# end of autoconf script
