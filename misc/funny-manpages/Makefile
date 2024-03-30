V =	2.3
COMMENT =	funny unix manpages

DIST_TUPLE +=	github ltworf funny-manpages ${V} .

CATEGORIES =	misc

# Custom license, various maintainers
PERMIT_PACKAGE =	Yes

do-install:
	cp ${WRKSRC}/man/grope.1fun ${WRKSRC}/man/egrope.1fun
	cp ${WRKSRC}/man/grope.1fun ${WRKSRC}/man/fgrope.1fun
	${INSTALL_MAN_DIR} ${PREFIX}/man/man{1,3,6}
	${INSTALL_MAN} ${WRKSRC}/man/*.1fun ${PREFIX}/man/man1/
	${INSTALL_MAN} ${WRKSRC}/man/*.3fun ${PREFIX}/man/man3/
	${INSTALL_MAN} ${WRKSRC}/man/*.6fun ${PREFIX}/man/man6/

.include <bsd.port.mk>