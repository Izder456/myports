ONLY_FOR_ARCHS =	amd64 i386

COMMENT = 		pangea software game bugdom for modern systems

V = 			1.3.4
PKGNAME = 		Bugdom
FULLPKGNAME = 		Bugdom-$V
GH_ACCOUNT = 		jorio
GH_PROJECT = 		bugdom
GH_TAGNAME = 		$V
DISTNAME = 		bugdom-$V

DISTFILES.a = 		ef94150e2dcec522e3099f4d03a4e8f2639f7232.zip
DIST_SUBDIR = 		bugdom
SITES.a = 		https://github.com/jorio/Pomme/archive/

CATEGORIES = 		games

HOMEPAGE = 		https://pangeasoft.net/bug

MAINTAINER = 		izzy Meyer <izder456@disroot.org>

# BY-NC-SA
PERMIT_PACKAGE =	Yes

COMPILER =		base-clang ports-gcc

MODULES = 		devel/cmake

# Dependencies
BUILD_DEPENDS =		devel/sdl2 \
					audio/libsamplerate
LIB_DEPENDS =  		devel/sdl2 \
					audio/libsamplerate
RUN_DEPENDS =		devel/sdl2 \
					audio/libsamplerate

WANTLIB += ${COMPILER_LIBCXX} GL SDL2 c m


NO_TEST = 		Yes

CFLAGS += 		-I${X11BASE}/include
CXXFLAGS += 		-I${X11BASE}/include

CONFIGURE_ARGS += 	-DCMAKE_BUILD_TYPE=Release \
			-DCMAKE_INSTALL_PREFIX=${LOCALBASE}

WRKDIST = 		${WRKDIR}/Bugdom-$V

post-extract:
	mkdir -p ${WRKDIST}/extern/Pomme
	mv ${WRKDIR}/Pomme-ef94150e2dcec522e3099f4d03a4e8f2639f7232/* \
	  ${WRKDIST}/extern/Pomme

do-install:
	mkdir -p ${PREFIX}/share/Bugdom
	cp ${WRKSRC}/README.md ${PREFIX}/share/Bugdom
	cp ${WRKSRC}/CHANGELOG.md ${PREFIX}/share/Bugdom
	cp ${WRKSRC}/COMMANDLINE.md ${PREFIX}/share/Bugdom
	cp ${WRKSRC}/LICENSE.md ${PREFIX}/share/Bugdom
	cp -r ${WRKBUILD}/Data ${PREFIX}/share/Bugdom
	mkdir -p ${PREFIX}/bin
	cp ${WRKBUILD}/Bugdom ${PREFIX}/bin
	mkdir -p ${PREFIX}/share/applications
	cp ${WRKSRC}/packaging/io.jor.bugdom.desktop ${PREFIX}/share/applications
	mkdir -p ${PREFIX}/share/icons
	cp ${WRKSRC}/packaging/io.jor.bugdom.png ${PREFIX}/share/icons

.include <bsd.port.mk>
