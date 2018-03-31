# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - capitalize port or not?
# - double check PERMIT_... 
# - add x11/qt5 somehow
# - replace /usr/local with ${LOCALBASE}

COMMENT =	integrated development environment for R
# COMMENT-foo =	???	for multi packages

V = 1.1.444

#DISTNAME =	???
#PKGNAME =	???

GH_ACCOUNT =	rstudio
GH_PROJECT =	rstudio
GH_TAGNAME =	v${V}
#GH_COMMIT =	abab123456789abacafeabab123123b1e4ble4bl

DICTIONARY_URL = https://s3.amazonaws.com/rstudio-dictionaries/core-dictionaries.zip
MATHJAX_URL =	https://s3.amazonaws.com/rstudio-buildtools/mathjax-26.zip

# for any port that creates shared libraries.
# both libtool and cmake automatically set filenames based on this variable.
# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =	???

# the category used in the directory name, /usr/ports/<category>/portname,
# must be included and listed first.
CATEGORIES =	math

#HOMEPAGE =	???	URL

# person who is responsible for the port. Use a complete email address with
# a real name, e.g., "MAINTAINER = John Doe <doe57@machine.somewhere.org>".
# If you maintain several ports, use the same line each time.
# If you no longer use the port, or are unwilling/unable to handle issues
# in a timely manner, *leave the field blank*.
# Default value is ports@openbsd.org, no need to fill in
MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

#GNU Affero GPLv3
PERMIT_PACKAGE_CDROM =	Yes

# If pledge is used, annotate with `uses pledge()' in a comment

# "make port-lib-depends-check" can help
#WANTLIB =		???

# where the source files and patches can be fetched
#
#MASTER_SITES =		???
#MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=subdir/}
#MASTER_SITES =		${MASTER_SITE_foo:=subdir/}

# if more master sites are needed...
#MASTER_SITES0 =
# ...
#DISTFILES =		???
#EXTRACT_ONLY =		???
#EXTRACT_SUFX =		.tar.bz2

#DIST_SUBDIR =		???

# PATCHFILES are also retrieved from MASTER_SITES*
#PATCHFILES =		???
#PATCH_DIST_STRIP =	-p0

MODULES =	devel/cmake
BUILD_DEPENDS =	devel/boost
#RUN_DEPENDS =		???
LIB_DEPENDS =	security/openpam \
		devel/llvm
#TEST_DEPENDS =		???

#MAKE_FLAGS =		???
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

# build/configuration variables
#
#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
#USE_GMAKE =		Yes
#USE_GROFF =		Yes
# Programs that require GNU libtool to build instead of the OpenBSD one
# should use this option. Add a comment explaining why. Don't use this if
# a port requires libtool's .m4 files but otherwise can use OpenBSD libtool,
# in that case use "BUILD_DEPENDS=devel/libtool" instead.
#USE_LIBTOOL=		gnu
# Set CONFIGURE_STYLE to value corresponding to some standard configuration
# 	  perl [modbuild]: perl's MakeMaker Makefile.PL (modbuild: perl's
#	  Module::Build Build.PL)
# 	  gnu [autoconf] [old] [dest]: gnu style configure (old: no
# 	  sysconfdir), (dest: add DESTDIR, does not handle it),
# 	  (autoconf: needed by port, implies gnu)
# 	XXX: cygnus products do NOT use autoconf for making the main
# 		configure from configure.in
# 	  imake [noman]: port uses imake for configuration.
#	  (noman: no man page installation)
# 	  simple: port has its own configure script
#CONFIGURE_STYLE =	
#CONFIGURE_SCRIPT =	??? (if other than configure)
CONFIGURE_ARGS =	-DCMAKE_BUILD_TYPE=Release
CONFIGURE_ENV =	Qt5Core_DIR=/usr/local/lib/qt5/cmake/Qt5Core/ \
		Qt5Widgets_DIR=/usr/local/lib/qt5/cmake/Qt5Widgets/ \
		Qt5Network_DIR=/usr/local/lib/qt5/cmake/Qt5Network/ \
		Qt5WebKit_DIR=/usr/local/lib/qt5/cmake/Qt5WebKit/ \
		Qt5WebChannel_DIR=/usr/local/lib/qt5/cmake/Qt5WebChannel/ \
		Qt5WebKitWidgets_DIR=/usr/local/lib/qt5/cmake/Qt5WebKitWidgets/ \
		Qt5PrintSupport_DIR=/usr/local/lib/qt5/cmake/Qt5PrintSupport/ \
		Qt5Quick_DIR=/usr/local/lib/qt5/cmake/Qt5Quick/ \
		Qt5Positioning_DIR=/usr/local/lib/qt5/cmake/Qt5Positioning/ \
		Qt5Sensors_DIR=/usr/local/lib/qt5/cmake/Qt5Sensors/ \
		Qt5Svg_DIR=/usr/local/lib/qt5/cmake/Qt5Svg/ \
		Qt5Xml_DIR=/usr/local/lib/qt5/cmake/Qt5Xml/ \
		Qt5XmlPatterns_DIR=/usr/local/lib/qt5/cmake/Qt5XmlPatterns/ \
		Qt5Sql_DIR=/usr/local/lib/qt5/cmake/Qt5Sql/ \
		Qt5OpenGL_DIR=/usr/local/lib/qt5/cmake/Qt5OpenGL/ \
		Qt5DBus_DIR=/usr/local/lib/qt5/cmake/Qt5DBus/

# for gnu stuff
#AUTOCONF_VERSION =	??? (defaults to 2.13)
#AUTOMAKE_VERSION =	??? (defaults to 1.4)
# config.guess and others are copied here
#MODGNU_CONFIG_GUESS_DIRS = ??? (defaults to ${WRKSRC})

# Is the build automagic or is it interactive
#
#IS_INTERACTIVE =		Yes
#TEST_IS_INTERACTIVE =		Yes

# Assume you have one multiple choice flavor: 1 2 3 and switches a b.
# You would write
#
#FLAVORS =	1 2 3 a b
#FLAVOR ?=
# grab multiple choice value
#CHOICE = ${FLAVOR:Na:Nb}
# check that CHOICE is 1 OR 2 OR 3, or error out
#.if ${CHOICE} == "1"
# code for 1
#.elif ${CHOICE} == "2"
# code for 2
#.elif ${CHOICE} == "3"
# code for 3
#.else
#ERRORS += "Fatal: Conflicting flavor: ${FLAVOR}"
#.endif
# check for switches
#.if ${FLAVOR:Ma}
# code for a
#.endif
#.if ${FLAVOR:Mb}
# code for b
#.endif

# Things that we don't want to do for this port/package
# Generally, DON'T set anything to No if it's not needed.
# The time gained is not worth it.
#
#NO_BUILD =		Yes
#NO_TEST =		Yes

# Overrides for default values
#
#CFLAGS =		???
#LDFLAGS =		???
#MAKE_FILE =		???
#PKG_ARCH =		??? (* for arch-independent packages)
#WRKDIST =		??? if other than ${WRKDIR}/${DISTNAME}
#WRKSRC =		??? if other than ${WRKDIST}
#WRKBUILD =		??? if other than ${WRKSRC}
#WRKCONF =		??? if other than ${WRKBUILD}

#ALL_TARGET =		???
#INSTALL_TARGET =	???
#TEST_TARGET =		???

post-extract:
	cd ${WRKSRC}/dependencies/common && mkdir -p dictionaries && \
		ftp ${MATHJAX_URL} && \
		unzip mathjax-26.zip && \
		rm mathjax-26.zip && \
		cd dictionaries && \
		ftp ${DICTIONARY_URL} && \
		unzip core-dictionaries.zip && \
		rm core-dictionaries.zip

.include <bsd.port.mk>
