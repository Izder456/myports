COMMENT =	deadbeef plugin for mpris2 support

V =	1.16
DIST_TUPLE +=	github DeaDBeeF-Player deadbeef-mpris2-plugin v${V} .
PKGNAME =	deadbeef-plugin-mpris2-${V}

CATEGORIES =	audio

HOMEPAGE =		https://github.com/DeaDBeeF-Player/deadbeef-mpris2-plugin

MAINTAINER =	izzy Meyer <izder456@disroot.org>

# GPL v2 only
PERMIT_PACKAGE =	Yes

WANTLIB +=	gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 gthread-2.0
WANTLIB +=	pthread iconv intl pcre2-8 z ffi

COMPILER =	base-clang ports-gcc


LIB_DEPENDS =	devel/pcre2
BUILD_DEPENDS =	devel/libtool \
				devel/libffi \
				devel/pcre2
RUN_DEPENDS =	audio/deadbeef

CONFIGURE_STYLE =	autoreconf

CONFIGURE_ENV +=	CPPFLAGS='-I${LOCALBASE}/include \
					-I${X11BASE}/include' \
					LDFLAGS='-L${LOCALBASE}/lib -L${X11BASE}/lib' \

CONFIGURE_ARGS =	--prefix ${LOCALBASE} \
					--disable-static

LIBTOOL_FLAGS =	--tag=disable-static

AUTOCONF_VERSION =	2.69
AUTOMAKE_VERSION =	1.16

post-install:
		@rm ${PREFIX}/lib/deadbeef/*.la

.include <bsd.port.mk>
