# $OpenBSD: Makefile.template,v 1.77 2018/02/09 17:08:33 sthen Exp $

# HINTS
# sthen | copy some way or another, then chown (BIN|SHARE)OWN:(BIN|SHARE)GRP,
#	chmod BINMODE/SHAREMODE
# sthen | pax -rw is somewhat common in parts of the ports tree

# TODO
# remove bundled lua!
# remove all the other bundled crap
# fix DISTDIR name, WRKDIR name etc
# ? should LICENSES folder be installed?
# create wrapperscript
# ? install Readme.md? in .../share/docs/cendric ?
# dialogue_tool.ini seems to not need to be in ~/.local/share...
#   -> not sure where the path to this .ini is set anyway
# is ext folder really needed in ${GAMEDIR}??
# {saves,src,tools} folder seems not to be needed in ${GAMEDIR}
# should *.ini be installed into the folder for example files? see porter's
#	handbook (/usr/local/share/examples/<name>)
# Maybe wrapper script should copy *.ini to ~/.local/share/cendric if they
#	don't exist
# if using bundled lua, remove MODULE lang/lua

COMMENT =	game that combines open platforming and role-playing 

DISTNAME =	Cendric_${GH_COMMIT}
#PKGNAME =	???

GH_ACCOUNT =	tizian
GH_PROJECT =	Cendric2
#GH_TAGNAME =	v0.9.0
GH_COMMIT =	db6f41890e9962198b8764a3583414b44d4af3e0

# for any port that creates shared libraries.
# both libtool and cmake automatically set filenames based on this variable.
# for libtool- or cmake-based ports, have a look at WRKBUILD/shared_libs.log
#SHARED_LIBS =	???

CATEGORIES =	games

HOMEPAGE =	https://cendric.ch	# https has invalid cert certificate

MAINTAINER =	Thomas Frohwein <frohwein@ymail.com>

# MIT (code), CC-BY-NC-SA-4.0 (assets)
PERMIT_PACKAGE_CDROM =  Non-commercial
PERMIT_PACKAGE_FTP =    Yes

#WANTLIB =		???

#MASTER_SITES =		https://github.com/tizian/Cendric2/releases/download/v0.9.0/

MODULES =		devel/cmake \
			lang/lua
#BUILD_DEPENDS =	???
#RUN_DEPENDS =		???
#LIB_DEPENDS =		???

CONFIGURE_ENV =	CPPFLAGS="-I${LOCALBASE}/include" LDFLAGS="-L${LOCALBASE}/lib"

GAMEDIR =	${PREFIX}/share/cendric

post-extract:
	rm -rf ${WRKSRC}/include/Steam
	rm -rf ${WRKSRC}/src/Steam

# the tree is still incomplete; waiting for input on best practices
do-install:
	${INSTALL_DATA_DIR} ${GAMEDIR}
	${INSTALL_DATA_DIR} ${GAMEDIR}/{db,ext,images,include,res}
	${INSTALL_DATA_DIR} ${GAMEDIR}/res/{npc,quest,font,texture,sound,music}
	${INSTALL_DATA_DIR} ${GAMEDIR}/res/texture/{screens,particles,items,spells,misc,cendric,debuffs,gui}
	${INSTALL_DATA_DIR} ${GAMEDIR}/res/sound/{tile,gui,item}
	${INSTALL_PROGRAM} ${WRKBUILD}/Cendric ${GAMEDIR}
	${INSTALL_DATA} ${WRKSRC}/*.ini ${GAMEDIR}
	${INSTALL_DATA} ${WRKSRC}/images/* ${GAMEDIR}/images

.include <bsd.port.mk>
