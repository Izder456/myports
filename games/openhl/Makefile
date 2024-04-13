COMMENT =	digital preservation of Half-Life

V =	1.0
PKGNAME =	openhl-$V

DIST_TUPLE +=	github osen openhl fee890e62e0794f236ab35ae7fc677c2c3ea70fe .

CATEGORIES =	games

HOMEPAGE =	https://github.com/osen/openhl

PERMIT_PACKAGE =	Yes

WANTLIB +=	${COMPILER_LIBCXX} c expat fontconfig freetype m

COMPILER =		base-clang ports-gcc base-gcc

BUILD_DEPENDS =	devel/sdl2 lang/mono lang/python/3.10 devel/cmake

do-build:
	cd ${WRKBUILD} && sh build.sh

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/xash3d
	cp -R ${WRKBUILD}/export/share/xash3d/* \
		${PREFIX}/share/xash3d/
	${INSTALL_DATA_DIR} ${PREFIX}/lib/xash3d
	cp -R ${WRKBUILD}/export/lib/xash3d/* \
		${PREFIX}/lib/xash3d/
	${INSTALL} ${WRKBUILD}/export/bin/* \
		${PREFIX}/bin/

.include <bsd.port.mk>