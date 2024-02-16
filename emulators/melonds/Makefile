COMMENT =	Nintendo DS emulator

# http://melonds.kuribo64.net/downloads.php
DIST_TUPLE +=	github melonDS-emu melonDS 0.9.5 .

CATEGORIES =	emulators

HOMEPAGE =	http://melonds.kuribo64.net/

MAINTAINER =	izzy Meyer <izder456@disroot.org>

# GPLv3+
PERMIT_PACKAGE =	Yes

COMPILER =	base-clang ports-gcc

WANTLIB +=	${COMPILER_LIBCXX} SDL2 atk-1.0 c cairo cairo-gobject
WANTLIB +=	gdk-3 gdk_pixbuf-2.0 gio-2.0 glib-2.0 gobject-2.0 gtk-3
WANTLIB +=	intl m pango-1.0 pangocairo-1.0

MODULES =		devel/cmake
LIB_DEPENDS =	devel/sdl2 \
				x11/gtk+3 \
				net/libslirp
BUILD_DEPENDS =	x11/qt5/qtbase

CONFIGURE_ARGS +=	-DQt5_DIR="${LOCALBASE}/lib/qt5/cmake/Qt5" \
					-DBUILD_STATIC=OFF \
					-DENABLE_JIT=OFF \
					-DENABLE_LTO_RELEASE=OFF \
					-DENABLE_LTO=OFF \
					-DCMAKE_BUILD_TYPE=Release

NO_TEST =		Yes

.include <bsd.port.mk>
