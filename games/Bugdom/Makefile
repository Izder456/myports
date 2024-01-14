ONLY_FOR_ARCHS =    amd64 i386

COMMENT =           pangea software game bugdom for modern systems

V =                 1.3.4
PKGNAME =           Bugdom
FULLPKGNAME =       Bugdom-$V
GH_ACCOUNT =        jorio
GH_PROJECT =        bugdom
GH_TAGNAME =        $V
DISTNAME =          bugdom-$V

DISTFILES.a =       ef94150e2dcec522e3099f4d03a4e8f2639f7232.zip
DIST_SUBDIR =       bugdom
SITES.a =           https://github.com/jorio/Pomme/archive/

CATEGORIES =        games

HOMEPAGE =          https://pangeasoft.net/bug

MAINTAINER =        izzy Meyer <izder456@disroot.org>

# BY-NC-SA
PERMIT_PACKAGE =    Yes

COMPILER =          base-clang ports-gcc

MODULES =           devel/cmake

BUILD_DEPENDS =     devel/sdl2 \
                    audio/libsamplerate
LIB_DEPENDS =       devel/sdl2
RUN_DEPENDS =       devel/sdl2 \
                    audio/libsamplerate \
                    devel/desktop-file-utils \
                    x11/gtk+4,-guic

WANTLIB +=          ${COMPILER_LIBCXX} GL SDL2 c m

NO_TEST =           Yes

CFLAGS +=           -I${X11BASE}/include
CXXFLAGS +=         -I${X11BASE}/include

CONFIGURE_ARGS +=   -DCMAKE_BUILD_TYPE=Release \
                    -DCMAKE_INSTALL_PREFIX=${LOCALBASE}

WRKDIST =           ${WRKDIR}/Bugdom-$V

post-extract:
	mkdir -p ${WRKDIST}/extern/Pomme
	mv ${WRKDIR}/Pomme-ef94150e2dcec522e3099f4d03a4e8f2639f7232/* \
	  ${WRKDIST}/extern/Pomme

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/Bugdom/
	${INSTALL_DATA} ${WRKSRC}/README.md ${PREFIX}/share/doc/Bugdom/
	${INSTALL_DATA} ${WRKSRC}/CHANGELOG.md ${PREFIX}/share/doc/Bugdom/
	${INSTALL_DATA} ${WRKSRC}/COMMANDLINE.md ${PREFIX}/share/doc/Bugdom/
	${INSTALL_DATA} ${WRKSRC}/LICENSE.md ${PREFIX}/share/doc/Bugdom/
	${INSTALL_DATA_DIR} ${PREFIX}/lib/Bugdom/
	${INSTALL_DATA_DIR} ${PREFIX}/lib/Bugdom/Data
	${INSTALL_PROGRAM} ${WRKBUILD}/Bugdom ${PREFIX}/lib/Bugdom/
	${INSTALL_SCRIPT} ${FILESDIR}/bugdom ${PREFIX}/bin/
	cp -rvf ${WRKBUILD}/Data ${PREFIX}/lib/Bugdom/
	${INSTALL_DATA_DIR} ${PREFIX}/share/icons/hicolor/512x512/apps/ \
		${PREFIX}/share/applications/
	${INSTALL_DATA} ${FILESDIR}/io.jor.bugdom.png \
		${PREFIX}/share/icons/hicolor/512x512/apps/
	${SUBST_CMD} -c -m ${SHAREMODE} -o ${SHAREOWN} -g ${SHAREGRP} \
		${FILESDIR}/io.jor.bugdom.desktop \
		${PREFIX}/share/applications/io.jor.bugdom.desktop

.include <bsd.port.mk>
