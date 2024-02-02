COMMENT = enhanced motif window manager (MWM fork)

GH_ACCOUNT = alx210
GH_PROJECT = emwm
GH_TAGNAME = v1.1

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
