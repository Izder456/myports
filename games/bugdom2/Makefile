COMMENT = sequel to the family-friendly 3D action adventure

V = 4.0.0

PKGNAME = bugdom2-${V}
DIST_TUPLE += github jorio Bugdom2 v${V} .
DIST_TUPLE += github jorio Pomme c6a38eab19a11847024a13f9b3e2af0c2d908c3e \
              extern/Pomme

CATEGORIES = games

HOMEPAGE = https://pangeasoft.net/bug2

MAINTAINER = izzy Meyer <izder456@disroot.org>

# CC-BY-NC SA 4.0
PERMIT_PACKAGE = Yes

WANTLIB += ${COMPILER_LIBCXX} GL SDL2 c m

# C++20
COMPILER =base-clang ports-gcc

MODULES = devel/cmake

BUILD_DEPENDS = audio/libsamplerate
LIB_DEPENDS = devel/sdl2
RUN_DEPENDS = audio/libsamplerate \
              devel/desktop-file-utils \
              x11/gtk+4,-guic

NO_TEST = Yes

CFLAGS += -I${X11BASE}/include
CXXFLAGS += -I${X11BASE}/include

CONFIGURE_ARGS += -DCMAKE_BUILD_TYPE=Release \
                  -DCMAKE_INSTALL_PREFIX=${LOCALBASE}

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/Bugdom2/
	${INSTALL_DATA} ${WRKSRC}/*.md ${PREFIX}/share/doc/Bugdom2/
	${INSTALL_DATA_DIR} ${PREFIX}/lib/Bugdom2/Data
	${INSTALL_PROGRAM} ${WRKBUILD}/Bugdom2 ${PREFIX}/lib/Bugdom2/
	${INSTALL_SCRIPT} ${FILESDIR}/bugdom2 ${PREFIX}/bin/
	cp -Rv ${WRKBUILD}/Data/* ${PREFIX}/lib/Bugdom2/Data
	${INSTALL_DATA_DIR} ${PREFIX}/share/icons/hicolor/512x512/apps/ \
		${PREFIX}/share/applications/
	${INSTALL_DATA} ${FILESDIR}/io.jor.bugdom2.png \
		${PREFIX}/share/icons/hicolor/512x512/apps/
	${SUBST_CMD} -c -m ${SHAREMODE} -o ${SHAREOWN} -g ${SHAREGRP} \
		${FILESDIR}/io.jor.bugdom2.desktop \
		${PREFIX}/share/applications/io.jor.bugdom2.desktop

.include <bsd.port.mk>
