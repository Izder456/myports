COMMENT =	deadbeef plugin for mpris2 support

V =		1.16
DIST_TUPLE +=	github DeaDBeeF-Player deadbeef-mpris2-plugin v${V} .
PKGNAME =	deadbeef-plugin-mpris2-${V}

CATEGORIES =	audio

MAINTAINER =	izzy Meyer <izder456@disroot.org>

# GPL v2 only
PERMIT_PACKAGE =	Yes

WANTLIB +=	gio-2.0 glib-2.0 gmodule-2.0 gobject-2.0 gthread-2.0
WANTLIB +=	pthread iconv intl pcre2-8 z ffi

LIB_DEPENDS =	devel/glib2 \
		devel/libffi \
		devel/pcre2
BUILD_DEPENDS =	audio/deadbeef \
		devel/libtool
RUN_DEPENDS =	audio/deadbeef

CONFIGURE_STYLE =	autoreconf

CPPFLAGS +=	-I${LOCALBASE}/include \
		-I${X11BASE}/include
LDFLAGS +=	-L${LOCALBASE}/lib \
		-L${X11BASE}/lib
CONFIGURE_ENV +=	CPPFLAGS='${CPPFLAGS}' \
			LDFLAGS='${LDFLAGS}'

LIBTOOL_FLAGS =	--tag=disable-static

AUTOCONF_VERSION =	2.71
AUTOMAKE_VERSION =	1.16

.include <bsd.port.mk>
