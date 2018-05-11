# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - double-check license
# - double-check that configuration done correctly
# - is audio/libsamplerate optional
# - error: opening file 'ships2.lbx'!
# - needs filenames to be lower case apparently

COMMENT =	clone of Master of Orion

V =		0.2
GH_ACCOUNT =	KilgoreTroutMaskReplicant
GH_PROJECT =	1oom
GH_TAGNAME =	v${V}

CATEGORIES =	games

MAINTAINER =	Thomas Frohwein <tfrohwein@fastmail.com>

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += GL SDL SDL_mixer c curses pthread readline

RUN_DEPENDS =	audio/libsamplerate
LIB_DEPENDS =	devel/sdl \
		devel/sdl-mixer

SEPARATE_BUILD =	Yes
CONFIGURE_STYLE =	gnu
AUTOCONF_VERSION =	2.69
AUTOMAKE_VERSION =	1.15

NO_TEST =		Yes

pre-configure:
	cd ${WRKSRC} && AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION} autoreconf -fi

.include <bsd.port.mk>
