# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - capitalize port or not?
# - double check PERMIT_... 
# - add x11/qt5 somehow
# - replace /usr/local with ${LOCALBASE}
# - binary is installed in @bin lib/rstudio/bin/rstudio
# - fix 'make plist'  Bogus element outside of every prefix
# $ /usr/local/lib/rstudio/bin/rstudio
# ld.so: rstudio: can't load library 'libinotify.so.2.1'
# - need to set --enable-R-shlib for build? so that it finds libR.so?
# - or fix this here:
#   src/cpp/core/r_util/REnvironmentPosix.cpp:#define kLibRFileName "libR.so"
# - doesn't really launch the interface - and just exits after a little
# - logs in ~/.rstudio-desktop/log
# - runs out of file descriptors, but not if uname -n 4096
# - apparently the build process creates files with some random, changing
#   names. This messes with the PLIST

COMMENT =	integrated development environment for R

V = 1.1.444

#DISTNAME =	???
#PKGNAME =	???

GH_ACCOUNT =	rstudio
GH_PROJECT =	rstudio
GH_TAGNAME =	v${V}

DICTIONARY_URL = https://s3.amazonaws.com/rstudio-dictionaries/core-dictionaries.zip
MATHJAX_URL =	https://s3.amazonaws.com/rstudio-buildtools/mathjax-26.zip
GWT_URL = https://s3.amazonaws.com/rstudio-buildtools/gwt-2.7.0.zip
GIN_URL = https://s3.amazonaws.com/rstudio-buildtools/gin-1.5.zip

# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =	???

CATEGORIES =	math

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

#GNU Affero GPLv3
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MODULES =	devel/cmake
BUILD_DEPENDS =	devel/boost \
		devel/apache-ant
LIB_DEPENDS =	security/openpam \
		devel/llvm \
		devel/libinotify
#TEST_DEPENDS =		???

CONFIGURE_ARGS =	-DCMAKE_BUILD_TYPE=Release \
			-DRSTUDIO_TARGET=Desktop
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

MAKE_ENV =	HOME=${WRKDIR} \
		ANT_OPTS="-Duser.home=${WRKDIR}"

#NO_TEST =		Yes

#TEST_TARGET =		???

post-extract:
	cd ${WRKSRC}/dependencies/common && mkdir -p dictionaries && \
		ftp ${MATHJAX_URL} && \
		unzip mathjax-26.zip && \
		rm mathjax-26.zip && \
		mkdir -p ../../src/gwt/lib/gwt && \
		ftp ${GWT_URL} && \
		unzip -d ../../src/gwt/lib/gwt gwt-2.7.0.zip && \
		mv ../../src/gwt/lib/gwt/{gwt-,}2.7.0 && \
		rm gwt-2.7.0.zip && \
		mkdir -p ../../src/gwt/lib/gin/1.5 && \
		ftp ${GIN_URL} && \
		unzip -d ../../src/gwt/lib/gin/1.5 gin-1.5.zip && \
		rm gin-1.5.zip && \
		cd dictionaries && \
		ftp ${DICTIONARY_URL} && \
		unzip core-dictionaries.zip && \
		rm core-dictionaries.zip

post-patch:
	sed -i "s,</java>,<jvmarg value=\"-Duser.home=${WRKDIR}\"/></java>,g" \
		${WRKSRC}/src/gwt/build.xml

.include <bsd.port.mk>
