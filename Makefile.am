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
#   @configure_input@
#
#   Makefile.am - automate compiling on a unix platform
#

# Sub directories
SUBDIRS					=
DIST_SUBDIRS				=


# install directories
localedir				= $(datadir)/locale
moduledir				= $(libexecdir)/$(PACKAGE_TARNAME)


# global flags
AM_LDFLAGS				= -L$(builddir)/lib
AM_LIBS					= $(LTLIBINTL)
AM_CFLAGS				= -W -Wall -Werror -O2
AM_CPPFLAGS				= $(CFLAGS_WARNINGS) \
					  -I$(top_srcdir)/include \
					  -I$(top_builddir)/include \
					  -DLIBEXECDIR="\"$(libexecdir)\"" \
					  -DMODULEDIR="\"$(moduledir)\"" \
					  -DSYSCONFDIR="\"$(sysconfdir)\""
AM_LIBTOOLFLAGS				=
ACLOCAL_AMFLAGS				= -I m4
DEFS					= -DLOCALEDIR="\"$(localedir)\"" @DEFS@


# items to build
bin_PROGRAMS				=
include_HEADERS				=
info_TEXINFOS				= doc/readme.texi
lib_LTLIBRARIES				=
man_MANS				=
sbin_PROGRAMS				=
sysconf_DATA				=


# macros for doc/readme.info
doc_readme_TEXINFOS			= doc/readme.texi \
					  doc/titlepage.texi \
					  doc/version-readme.texi


# miscellaneous lists
CLEANFILES				= $(builddir)/a.out   $(srcdir)/a.out \
					  $(builddir)/*/a.out $(srcdir)/*/a.out \
					  config.h.in~ $(srcdir)/config.h.in~ \
					  stamp-vti $(srcdir)/stamp-vti \
					  $(man_MANS) \
					  @PACKAGE_TARNAME@-*.tar.* \
					  @PACKAGE_TARNAME@-*.zip
EXTRA_DIST				= COPYING.DOC \
					  COPYING.LIB \
					  build-aux/git-package-version \
					  visa.tags
EXTRA_PROGRAMS				=
EXTRA_TEXINFOS				=
TESTS					=
XFAIL_TESTS				=


# substitution routine
do_subst = sed \
		-e 's,[@]SHELL[@],@SHELL@,g' \
		-e 's,[@]PACKAGE_VERSION[@],@PACKAGE_VERSION@,g' \
		-e 's,[@]PACKAGE_NAME[@],@PACKAGE_NAME@,g' \
		-e 's,[@]PACKAGE_TARNAME[@],@PACKAGE_TARNAME@,g' \
		-e 's,[@]PACKAGE_BUGREPORT[@],@PACKAGE_BUGREPORT@,g' \
		-e 's,[@]GIT_PACKAGE_VERSION[@],@GIT_PACKAGE_VERSION@,g' \
		-e 's,[@]INSTALL[@],$(INSTALL),g' \
		-e 's,[@]INSTALL_PROGRAM[@],$(INSTALL_PROGRAM),g' \
		-e 's,[@]INSTALL_SCRIPT[@],$(INSTALL_SCRIPT),g' \
		-e 's,[@]INSTALL_DATA[@],$(INSTALL_DATA),g' \
		-e 's,[@]prefix[@],$(prefix),g' \
		-e 's,[@]datadir[@],$(datadir),g' \
		-e 's,[@]sysconfdir[@],$(sysconfdir),g' \
		-e 's,[@]moduledir[@],$(moduledir),g'
do_subst_fn = \
		echo "do_subst < ${@}.in > ${@}"; \
		mkdir -p `dirname ${@}` || exit 1; \
		${do_subst} < $(srcdir)/${@}.in > ${@} || exit 1; \
		chmod 0755 ${@}
do_subst_dt = \
		echo "do_subst < ${@}.in > ${@}"; \
		mkdir -p `dirname ${@}` || exit 1; \
		${do_subst} < $(srcdir)/${@}.in > ${@} || exit 1; \
		chmod 0644 ${@}


# custom targets
build-aux/git-package-version:
	mkdir -p build-aux
	echo $(PACKAGE_VERSION) > $(srcdir)/build-aux/git-package-version


# local targets
clean-local:

distclean-local:
	-rm -fR $(srcdir)/autom4te.cache	# removes autoconf cache

install-exec-local:

install-data-local:

install-exec-hook:

install-data-hook:

uninstall-local:

uninstall-hook:

# end of autmake script
