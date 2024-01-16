COMMENT = family-friendly stone-age 3D kart racing game

# Commit id fixed the ByteSwap terrain compile-time error
# (latest ID as of writing)

V = 3.0.0
C =	5983de40c180b50bbbec8b04f5f5f1ceccd1901b
PKGNAME = cromagrally-${V}
DIST_TUPLE += github jorio CroMagRally ${C} .
DIST_TUPLE += github jorio Pomme d57c28e205462e51063e787f9ebddaadff592f1e \
              extern/Pomme
DISTNAME = CroMagRally-${C}

CATEGORIES = games

HOMEPAGE = https://pangeasoft.net/cromag

MAINTAINER = izzy Meyer <izder456@disroot.org>

# CC-BY-NC SA 4.0
PERMIT_PACKAGE = Yes

WANTLIB += ${COMPILER_LIBCXX} GL SDL2 c m

# C++20
COMPILER = base-clang ports-gcc

MODULES = devel/cmake

BUILD_DEPENDS = audio/libsamplerate
LIB_DEPENDS = devel/sdl2
RUN_DEPENDS = audio/libsamplerate \
              devel/desktop-file-utils \
              x11/gtk+4,-guic

NO_TEST =           Yes

CFLAGS += -I${X11BASE}/include
CXXFLAGS += -I${X11BASE}/include

CONFIGURE_ARGS += -DCMAKE_BUILD_TYPE=Release \
                  -DCMAKE_INSTALL_PREFIX=${LOCALBASE}

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/CroMagRally/
	${INSTALL_DATA} ${WRKSRC}/*.md ${PREFIX}/share/doc/CroMagRally/
	${INSTALL_DATA_DIR} ${PREFIX}/lib/CroMagRally/Data
	${INSTALL_PROGRAM} ${WRKBUILD}/CroMagRally ${PREFIX}/lib/CroMagRally/
	${INSTALL_SCRIPT} ${FILESDIR}/cromagrally ${PREFIX}/bin/
	cp -Rv ${WRKBUILD}/Data/* ${PREFIX}/lib/CroMagRally/Data
	${INSTALL_DATA_DIR} ${PREFIX}/share/icons/hicolor/512x512/apps/ \
		${PREFIX}/share/applications/
	${INSTALL_DATA} ${FILESDIR}/cromagrally-desktopicon.png \
		${PREFIX}/share/icons/hicolor/512x512/apps/
	${SUBST_CMD} -c -m ${SHAREMODE} -o ${SHAREOWN} -g ${SHAREGRP} \
		${FILESDIR}/cromagrally.desktop \
		${PREFIX}/share/applications/cromagrally.desktop

.include <bsd.port.mk>
