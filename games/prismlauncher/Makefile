COMMENT =		free and open-source launcher for Minecraft


V =		8.4
PKGNAME =	prismlauncher-${V}

DIST_TUPLE +=	github PrismLauncher PrismLauncher ${V} .
DIST_TUPLE +=	github commonmark cmark \
		8fbf029685482827828b5858444157052f1b0a5f ./libraries/cmark
DIST_TUPLE +=	github gulrak filesystem \
		2fc4b463759e043476fc0036da094e5877e3dd50 ./libraries/filesystem
DIST_TUPLE +=	github PrismLauncher libnbtplusplus \
		23b955121b8217c1c348a9ed2483167a6f3ff4ad ./libraries/libnbtplusplus
DIST_TUPLE +=	github stachenov quazip \
		9d3aa3ee948c1cde5a9f873ecbc3bb229c1182ee ./libraries/quazip
DIST_TUPLE +=	github marzer tomlplusplus \
		7eb2ffcc09f8e9890dc0b77ff8ab00fc53b1f2b8 ./libraries/tomlplusplus

CATEGORIES =		games

HOMEPAGE =		https://prismlauncher.org

# GPLv3+ libraries/launcher
# LGPLv3+ libraries/libnbtplusplus, LGPLv2 libraries/rainbow
# BSD libraries/cmark, MIT libraries/lionshead
# MIT libraries/tomlplusplus, MIT libraries/filesystem
PERMIT_PACKAGE =	Yes

WANTLIB +=		${COMPILER_LIBCXX} GL Qt6Concurrent Qt6Core Qt6Core5Compat
WANTLIB +=		Qt6Gui Qt6Network Qt6Widgets Qt6Xml bz2 c cmark m z

MODULES =		devel/cmake \
			x11/qt6 \
			java
MODJAVA_VER =		17

RUN_DEPENDS =		audio/openal \
			games/lwjgl3 \
			x11/gtk+4,-guic \
			devel/desktop-file-utils \
			misc/shared-mime-info
LIB_DEPENDS =		x11/qt6/qt5compat \
			textproc/cmark

CONFIGURE_ARGS =	-DCMAKE_BUILD_TYPE=Release \
			-DCMAKE_INSTALL_PREFIX="${LOCALBASE}" \
			-DENABLE_LTO=ON \
			-DLauncher_BUILD_PLATFORM="openbsd" \
			-DLauncher_QT_VERSION_MAJOR="6" \
			-Dorg.lwjgl.librarypath="${LOCALBASE}/share/lwjgl"

.include <bsd.port.mk>
