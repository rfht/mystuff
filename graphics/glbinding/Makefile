# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - double-check license
# - set MODPY_VERSION
# - replace include dir with X11BASE and use SUBST_CMD
# - check how to enable src/tests

COMMENT =	C++ binding for the OpenGL API

GH_ACCOUNT =	cginternals
GH_PROJECT =	glbinding
GH_TAGNAME =	v2.1.4

SHARED_LIBS +=  glbinding                 0.0 # 2.1

CATEGORIES =	graphics

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# MIT
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${COMPILER_LIBCXX} GL GLU c glfw m

MODULES =	devel/cmake
LIB_DEPENDS =	graphics/glfw

CONFIGURE_ARGS =	-Dglfw3_DIR="${LOCALBASE}/lib/cmake/glfw3"

#NO_TEST =		Yes

.include <bsd.port.mk>
