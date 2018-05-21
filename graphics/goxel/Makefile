# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# - double-check license
# - doesn't honor CXXFLAGS
# - -Ofast in calls to clang and clang++
# - double-check what's done in configure stage
# - seems to create imgui.ini in current working directory
# - SEPARATE_BUILD doesn't work for this
# - add arches code to not set clang=1 on non-clang arches

COMMENT =	free and open source 3D voxel editor

GH_ACCOUNT =	guillaumechereau
GH_PROJECT =	goxel
GH_TAGNAME =	v0.8.0

CATEGORIES =	graphics

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# GPLv3
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} GL X11 Xau Xcomposite Xcursor Xdamage
WANTLIB += Xdmcp Xext Xfixes Xi Xinerama Xrandr Xrender atk-1.0
WANTLIB += atk-bridge-2.0 atspi c cairo cairo-gobject dbus-1 epoxy
WANTLIB += expat fontconfig freetype fribidi gdk-3 gdk_pixbuf-2.0
WANTLIB += gio-2.0 glfw glib-2.0 gmodule-2.0 gobject-2.0 graphite2
WANTLIB += gtk-3 harfbuzz intl m pango-1.0 pangocairo-1.0 pangoft2-1.0
WANTLIB += pcre pixman-1 png xcb xcb-render xcb-shm z

MODULES =	devel/scons
BUILD_DEPENDS =	devel/argp-standalone
LIB_DEPENDS =	devel/pango \
		devel/pcre \
		graphics/glfw \
		graphics/png \
		x11/gtk+3

MODSCONS_FLAGS =	clang=1 \
			debug=0

NO_TEST =		Yes

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/goxel ${PREFIX}/bin

.include <bsd.port.mk>
