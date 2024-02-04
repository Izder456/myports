COMMENT = session manager and a toolchest-like application launcher.

V = 1.2
SITES = https://fastestcode.org/dl/
DISTNAME = emwm-utils-src-${V}
PKGNAME = emwm-utils-${V}
EXTRACT_SUFX = .tar.xz

CATEGORIES = x11

HOMEPAGE = https://fastestcode.org/emwm.html

MAINTAINER = izzy Meyer <izder456@disroot.org>

# MIT
PERMIT_PACKAGE = Yes

LIB_DEPENDS = x11/motif

WANTLIB +=	X11 Xext Xinerama Xm Xrandr Xt c m

NO_TEST = Yes

FAKE_FLAGS = PREFIX=${WRKINST}${PREFIX}

.include <bsd.port.mk>
