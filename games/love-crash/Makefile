# $OpenBSD: Makefile,v 1.22 2017/07/26 22:45:21 sthen Exp $

COMMENT=		2D games framework for use with Lua

V=			0.10.2
DISTNAME=		love-$V-linux-src
PKGNAME=		love-$V

SHARED_LIBS +=  love                      0.0 # 0.0

HOMEPAGE=		http://love2d.org/

CATEGORIES=		games lang/lua

# code: zlib license
# docs: freebsd license
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ${MODLUA_WANTLIB}
WANTLIB += c
WANTLIB += freetype m modplug mpg123
WANTLIB += ogg openal physfs pthread sndio ${COMPILER_LIBCXX}
WANTLIB += usbhid vorbis vorbisfile
WANTLIB += z
WANTLIB += stdc++
WANTLIB += SDL2 samplerate
WANTLIB += luajit-5.1 theoradec

MASTER_SITES=		https://bitbucket.org/rude/love/downloads/

MODULES=		lang/lua

RUN_DEPENDS=		x11/gtk+3,-guic \
			devel/desktop-file-utils \
			misc/shared-mime-info

LIB_DEPENDS=		audio/libmodplug \
			audio/mpg123 \
			audio/openal \
			audio/libvorbis \
			devel/physfs \
			${MODLUA_LIB_DEPENDS} \
			devel/sdl2 \
			lang/luajit \
			multimedia/libtheora

CONFIGURE_STYLE=	gnu
CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include -I${LOCALBASE}/include/SDL/ \
				-I${X11BASE}/include/ -I${X11BASE}/include/freetype2 \
				`pkg-config --cflags ${MODLUA_DEP}`" \
			LDFLAGS="-L${X11BASE}/lib -L${LOCALBASE}/lib -pthread"

WRKDIST=		${WRKDIR}/love-$V

post-extract:
# Add missing newlines
	cd ${WRKSRC} && \
		for i in `find . -type f`; \
			do [ "$(tail -c1 $i)" == "$(printf '\n')" ] || ls -l $i; \
		done

.include <bsd.port.mk>
