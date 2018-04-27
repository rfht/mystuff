# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - clarify: it fetches C# dependencies as part of make all
# - most data is installed under PREFIX/lib, not PREFIX/share
# - uses packaged glsl and lua??
# - looks for zenity (x11/gnome/zenity - for dialog boxes) ?? not reproduced
# - several external config files need entry for openbsd:
#   - SDL2-CS.dll.config
#   - OpenAL-CS.dll.config
#   - SharpFont.dll.config
# - DNS lookup failure when trying to fetch assets
# - has telemetry; should maybe be turned off:
#   - https://github.com/OpenRA/OpenRA/wiki/Settings

COMMENT =	open-source real-time strategy game engine

V =	20180307

DISTNAME =	OpenRA-release-${V}-source
PKGNAME =	openra-${V}

#GH_ACCOUNT =	OpenRA
#GH_PROJECT =	OpenRA
#GH_TAGNAME =	1.0

#GEOLITE =	GeoLite2-Country.mmdb
#STYLECOPPLUS =	1.9
#STYLECOP =	StyleCop.StyleCop.2016.1.0
#MAXMINDDB =	maxmind.db.2.0.0
#SHARPFONT =	v4.0.1
#OPENNAT =	open.nat.2.1.0
#FUZZYLOGIC =	fuzzylogiclibrary.1.2.0
#RIX0RRR =	rix0rrr.beaconlib.1.0.1
#GEOIP_DB =	GeoLite2-Country.mmdb
#SDL2_CS =	SDL2-CS.dll
#OPENAL_CS =	OpenAL-CS.dll
#ELUANT =	Eluant.dll

# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =	???

CATEGORIES =	games

HOMEPAGE =	https://www.openra.net

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

#GPLv3
PERMIT_PACKAGE_CDROM =	Yes

#WANTLIB =		???

MASTER_SITES =  https://github.com/OpenRA/OpenRA/releases/download/release-${V}/

EXTRACT_SUFX =		.tar.bz2

#MASTER_SITES0 =	https://geolite.maxmind.com/download/geoip/database/
#MASTER_SITES1 = https://github.com/shuruev/StyleCopPlus/archive/
#MASTER_SITES2 = https://github.com/StyleCop/StyleCop/releases/download/resharper-2016.1.0/
#MASTER_SITES3 =	https://www.nuget.org/api/v2/package/MaxMind.Db/2.0.0/
#MASTER_SITES4 = https://github.com/Robmaister/SharpFont/archive/
#MASTER_SITES5 = https://www.nuget.org/api/v2/package/Open.Nat/2.1.0/
#MASTER_SITES6 = https://www.nuget.org/api/v2/package/FuzzyLogicLibrary/1.2.0/
#MASTER_SITES7 = https://www.nuget.org/api/v2/package/rix0rrr.BeaconLib/1.0.1/
#MASTER_SITES8 = https://geolite.maxmind.com/download/geoip/database/
#MASTER_SITES9 = https://github.com/OpenRA/SDL2-CS/releases/download/20161223/
#MASTER_SITES10=	https://github.com/OpenRA/OpenAL-CS/releases/download/20151227/
#MASTER_SITES11=	https://github.com/OpenRA/Eluant/releases/download/20160124/

#DISTFILES =	${DISTNAME}${EXTRACT_SUFX}
#${GEOLITE}.gz:0
#${STYLECOPPLUS}.tar.gz:1
#${STYLECOP}.nupkg:2
#${MAXMINDDB}.nupkg:3
#${SHARPFONT}.tar.gz:4
#${OPENNAT}.nupkg:5
#${FUZZYLOGIC}.nupkg:6
#${RIX0RRR}.nupkg:7
#${GEOIP_DB}.gz:8
#${SDL2_CS}:9
#${OPENAL_CS}:10
#${ELUANT}:11

MODULES =	lang/mono
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
#LIB_DEPENDS =		???
#TEST_DEPENDS =		???

#MAKE_FLAGS =		???
#MAKE_ENV =		???
#FAKE_FLAGS =		???
#TEST_FLAGS =		???

# build/configuration variables
#
#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
#SEPARATE_BUILD =	flavored (distinct flavors may share a common WRKSRC)
USE_GMAKE =		Yes
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
#CONFIGURE_ARGS =	???
#CONFIGURE_ENV =	???

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
WRKDIST =		${WRKDIR}
#WRKSRC =		??? if other than ${WRKDIST}
#WRKBUILD =		??? if other than ${WRKSRC}
#WRKCONF =		??? if other than ${WRKBUILD}

#ALL_TARGET =		???
#INSTALL_TARGET =	???
#TEST_TARGET =		???

post-install:
	cd ${WRKSRC} && ${MAKE_PROGRAM} install-linux-shortcuts

.include <bsd.port.mk>
