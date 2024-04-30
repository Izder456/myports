COMMENT =	fork of xbelld, the X bell daemon for machines w/o a pcspkr

V =	0.1.2
PKGNAME =	nxbelld-$V

DIST_TUPLE +=	github dusxmt nxbelld $V .

CATEGORIES =	x11

HOMEPAGE =	https://github.com/dusxmt/nxbelld

MAINTAINER =	izzy Meyer <izder456@disroot.org>

# GPL v3+
PERMIT_PACKAGE =	Yes

WANTLIB +=	X11 c m sndio

COMPILER =	base-clang ports-gcc base-gcc

USE_GMAKE =	Yes

CONFIGURE_STYLE =	autoreconf

AUTOCONF_VERSION =	2.71
AUTOMAKE_VERSION =	1.16

.include <bsd.port.mk>
