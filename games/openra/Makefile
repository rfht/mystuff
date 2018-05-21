# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# TODO:
# - clarify: it fetches C# dependencies as part of make all
# - most data is installed under PREFIX/lib, not PREFIX/share
# - uses packaged glsl and lua??
# - several external config files need entry for openbsd:
#   - SDL2-CS.dll.config
#   - OpenAL-CS.dll.config
#   - SharpFont.dll.config
# - has telemetry; should maybe be turned off:
#   - https://github.com/OpenRA/OpenRA/wiki/Settings
#   - seems to be opt-in during the game
# - upload repo of thirdparty stuff that's now in ~/obsd/ports/openra-libs
# - files are in ${WRKDIR}, not a subfolder

COMMENT =	open-source real-time strategy game engine

V =	20180307

DISTNAME =	OpenRA-release-${V}-source
PKGNAME =	openra-${V}

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
#LIB_DEPENDS =		???

#SEPARATE_BUILD =	Yes (build in a directory other than WRKSRC)
USE_GMAKE =		Yes

#NO_BUILD =		Yes
NO_TEST =	Yes

WRKDIST =		${WRKDIR}
#WRKSRC =		??? if other than ${WRKDIST}

post-install:
	cd ${WRKSRC} && ${MAKE_PROGRAM} install-linux-shortcuts

.include <bsd.port.mk>
