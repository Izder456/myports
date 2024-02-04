COMMENT = enhanced motif window manager (MWM fork)

V = 1.2
SITES = https://fastestcode.org/dl/
DISTNAME = emwm-src-${V}
PKGNAME = emwm-${V}
EXTRACT_SUFX = .tar.xz

CATEGORIES = x11

HOMEPAGE = https://fastestcode.org/emwm.html

MAINTAINER = izzy Meyer <izder456@disroot.org>

# LGPL v2.1
PERMIT_PACKAGE = Yes

LIB_DEPENDS = x11/motif

WANTLIB +=	X11 Xext Xinerama Xm Xrandr Xt c m

NO_TEST = Yes

FAKE_FLAGS = PREFIX=${WRKINST}${PREFIX}

.include <bsd.port.mk>
