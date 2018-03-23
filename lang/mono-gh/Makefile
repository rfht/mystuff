# $OpenBSD: Makefile,v 1.115 2018/01/16 16:12:54 robert Exp $

USE_WXNEEDED=	Yes

#BROKEN=		unreliable build, frequently segfaults in dpb (TLS?)

COMMENT=	cross platform, open source .NET developement framework

#V=		5.8.0.127
#DISTNAME=	mono-${V}

CATEGORIES=	lang devel

SHARED_LIBS +=  mono-2.0		0.0	# .0.0
SHARED_LIBS +=  monoboehm-2.0           1.0     # .0.0
SHARED_LIBS +=  monosgen-2.0            0.0	# .1.0
SHARED_LIBS +=  mono-profiler-iomap	0.0	# .0.0
SHARED_LIBS +=  mono-profiler-aot	1.0	# .0.0
SHARED_LIBS +=  mono-profiler-coverage	0.0	# .0.0
SHARED_LIBS +=  mono-profiler-log	0.0	# .0.0

HOMEPAGE=	http://www.mono-project.com/

MAINTAINER=	Robert Nagy <robert@openbsd.org>

# GPLv2, LGPL, MIT X11, MPL
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	c iconv m pthread z

#MASTER_SITES=	https://download.mono-project.com/sources/mono/
#EXTRACT_SUFX=	.tar.bz2

GH_ACCOUNT=	mono
GH_PROJECT=	mono
GH_TAGNAME=	mono-5.10.0.154

MODULES=	lang/mono \
		lang/python

MODMONO_DEPS=	No

USE_GMAKE=	Yes

SUBST_VARS=	LIBTOOL

BUILD_DEPENDS=	devel/bison \
		devel/gettext-tools \
		devel/cmake \
		lang/gawk \
		shells/bash \
		${RUN_DEPENDS} \
		${MODGNU_AUTOCONF_DEPENDS} \
		${MODGNU_AUTOMAKE_DEPENDS}

RUN_DEPENDS=	x11/libgdiplus

LIB_DEPENDS=	converters/libiconv

USE_LIBTOOL=	gnu

AUTOCONF_VERSION=	2.69
AUTOMAKE_VERSION=	1.15

AUTO_ENV=	AUTOCONF_VERSION=${AUTOCONF_VERSION} \
		AUTOMAKE_VERSION=${AUTOMAKE_VERSION}

TEST_DEPENDS=	lang/python/${MODPY_VERSION}

CONFIGURE_STYLE=autoconf automake
CONFIGURE_ENV=	LDFLAGS="-L${LOCALBASE}/lib" \
		CPPFLAGS="-I${LOCALBASE}/include" \
		ac_cv_header_execinfo_h=no \
		ac_cv_header_pthread_np_h=yes \
		MONO_ENABLE_LOCK_TRACER=1

.if ${MACHINE_ARCH} == "i386"
CONFIGURE_ENV+=	CFLAGS="-march=i586"
.endif

CONFIGURE_ARGS=	--with-gc=included \
		--with-tls=pthread \
		--disable-btls \
		--disable-quiet-build \
		--disable-shared-handles \
		--without-sigaltstack \
		--with-cooperative-gc=yes

MAKE_ENV=	MONO_ENABLE_LOCK_TRACER=1 \
		V=1

#DEBUG
CFLAGS=	-O0 -pipe -g

TEST_TARGET=check

DLLMAP_FILES=	mcs/class/System.Windows.Forms/System.Windows.Forms/MimeIcon.cs \
		mcs/tools/mono-shlib-cop/mono-shlib-cop.exe.config \
		mcs/class/System/System.IO/FAMWatcher.cs \
		mcs/class/System.Windows.Forms/System.Windows.Forms/X11DesktopColors.cs \
		mcs/class/Mono.Cairo/Samples/gtk/OldAndBusted.cs \
		data/config

FAKE_FLAGS=	sysconfdir=${PREFIX}/share/examples

post-extract:
	mv ${WRKSRC}/mono/mini/Makefile.am{.in,}

post-patch:
	cd ${WRKSRC}; ${AUTO_ENV} autoreconf -i --force -I ${WRKSRC}/mono/mini && \
	cd ${WRKSRC}; ${AUTO_ENV} aclocal -I . -I m4

pre-configure:
	cd ${WRKSRC} && ${AUTO_ENV} automake --foreign --add-missing
	${SUBST_CMD} ${WRKSRC}/runtime/mono-wrapper.in \
		${WRKSRC}/runtime/monodis-wrapper.in
	sed -i -e 's,^prefix=.*,prefix=\@prefix\@,g;' \
		-e 's,^exec_prefix=.*,exec_prefix=\@prefix\@,g' \
		${WRKSRC}/data/*.pc.in
	sed -i -e 's,/usr/bin/env python,${MODPY_BIN},g' \
		${WRKSRC}/mono/tests/gc-descriptors/gen-descriptor-tests.py

	@ln -fs /usr/local/bin/bash ${WRKDIR}/bin/bash
	@ln -fs /usr/local/bin/gawk ${WRKDIR}/bin/gawk
	@ln -fs ${MODPY_BIN} ${WRKDIR}/bin/python

# Force using the internal mcs compiler
pre-build:
	@mkdir -p ${WRKSRC}/mcs/build/deps
	@touch ${WRKSRC}/mcs/build/deps/use-monolite

# XXX stop mono failing the first time
# make _tmpinst more available
post-build:
	for i in ${WRKBUILD}/runtime/_tmpinst/bin/*; do \
		ln -fs $$i ${WRKDIR}/bin; \
	done

.include <bsd.port.mk>
