ONLY_FOR_ARCHS =	amd64 i386

COMMENT =         pangea software game bugdom 2 for modern systems

V =               4.0.0
PKGNAME =         Bugdom2
FULLPKGNAME =     Bugdom2-$V
GH_ACCOUNT =      jorio
GH_PROJECT =      bugdom2
GH_TAGNAME =      v$V
DISTNAME =        bugdom2-$V

DISTFILES.a =     c6a38eab19a11847024a13f9b3e2af0c2d908c3e.zip
DIST_SUBDIR =     bugdom2
SITES.a =         https://github.com/jorio/Pomme/archive/

CATEGORIES =      games

HOMEPAGE =        https://pangeasoft.net/bug2

MAINTAINER =      izzy Meyer <izder456@disroot.org>

# BY-NC-SA
PERMIT_PACKAGE =  Yes

COMPILER =        base-clang ports-gcc

MODULES =         devel/cmake

BUILD_DEPENDS =   devel/sdl2 \
                  audio/libsamplerate
LIB_DEPENDS =  		devel/sdl2
RUN_DEPENDS =     devel/sdl2 \
                  audio/libsamplerate \
                  devel/desktop-file-utils \
                  x11/gtk+4,-guic

WANTLIB +=        ${COMPILER_LIBCXX} GL SDL2 c m


NO_TEST =         Yes

CFLAGS +=         -I${X11BASE}/include
CXXFLAGS +=       -I${X11BASE}/include

CONFIGURE_ARGS += -DCMAKE_BUILD_TYPE=Release \
                  -DCMAKE_INSTALL_PREFIX=${LOCALBASE}

WRKDIST =         ${WRKDIR}/Bugdom2-$V

post-extract:
	mkdir -p ${WRKDIST}/extern/Pomme
	mv ${WRKDIR}/Pomme-c6a38eab19a11847024a13f9b3e2af0c2d908c3e/* \
	  ${WRKDIST}/extern/Pomme

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/Bugdom2/
	${INSTALL_DATA} ${WRKSRC}/README.md ${PREFIX}/share/doc/Bugdom2/
	${INSTALL_DATA} ${WRKSRC}/CHANGELOG.md ${PREFIX}/share/doc/Bugdom2/
	${INSTALL_DATA} ${WRKSRC}/SECRETS.md ${PREFIX}/share/doc/Bugdom2/
	${INSTALL_DATA} ${WRKSRC}/LICENSE.md ${PREFIX}/share/doc/Bugdom2/
	${INSTALL_DATA_DIR} ${PREFIX}/lib/Bugdom2/
	${INSTALL_DATA_DIR} ${PREFIX}/lib/Bugdom2/Data
	${INSTALL_PROGRAM} ${WRKBUILD}/Bugdom2 ${PREFIX}/lib/Bugdom2/
	${INSTALL_SCRIPT} ${FILESDIR}/bugdom2 ${PREFIX}/bin/
	cp -rvf ${WRKBUILD}/Data ${PREFIX}/lib/Bugdom2/
	${INSTALL_DATA_DIR} ${PREFIX}/share/icons/hicolor/512x512/apps/ \
		${PREFIX}/share/applications/
	${INSTALL_DATA} ${FILESDIR}/io.jor.bugdom2.png \
		${PREFIX}/share/icons/hicolor/512x512/apps/
	${SUBST_CMD} -c -m ${SHAREMODE} -o ${SHAREOWN} -g ${SHAREGRP} \
		${FILESDIR}/io.jor.bugdom2.desktop \
		${PREFIX}/share/applications/io.jor.bugdom2.desktop

.include <bsd.port.mk>
