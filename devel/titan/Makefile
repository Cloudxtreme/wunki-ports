# $FreeBSD$

PORTNAME=	titan
PORTVERSION=	0.0.1
CATEGORIES=	devel
PKGNAMEPREFIX=	gibbon-

MAINTAINER=	petar@gibbon.co
COMMENT=	Central API for Gibbon

LICENSE=	APACHE20

BUILD_DEPENDS=	${LOCALBASE}/bin/go:${PORTSDIR}/lang/go

USE_GITHUB=	yes
GH_ACCOUNT=	gibbonco
GH_TAGNAME=	${GH_COMMIT}
GH_COMMIT=	a381ff0

PLIST_FILES=	bin/tt

PORTDOCS=	README.md

OPTIONS_DEFINE=	DOCS
DOCS_DESC=	Install titan README file

.include <bsd.port.options.mk>

do-build:
	cd ${WRKSRC}; ${SH} build

do-install:
.if ${PORT_OPTIONS:MDOCS}
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/${PORTDOCS} ${STAGEDIR}${DOCSDIR}
.endif
	${INSTALL_PROGRAM} ${WRKSRC}/bin/bench ${STAGEDIR}${PREFIX}/bin/
	${INSTALL_PROGRAM} ${WRKSRC}/bin/etcd ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
