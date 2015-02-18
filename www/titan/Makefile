PORTNAME=	titan
DISTVERSION= 0.0.1-37

CATEGORIES=	www
MASTER_SITES=	https://s3.amazonaws.com/gibbon-deployment/

MAINTAINER=	petar@wunki.org
COMMENT=	Central API for Gibbon

LICENSE=	MPL

BUILD_DEPENDS=	${LOCALBASE}/bin/go:${PORTSDIR}/lang/go\
	${LOCALBASE}/bin/git:${PORTSDIR}/devel/git

USES=		compiler
STRIP=		# stripping can break go binaries

post-patch:
	${MKDIR} ${WRKSRC}/src/github.com/gibbonco
	@ln -s ${WRKSRC} ${WRKSRC}/src/github.com/gibbonco/titan

do-build:
	@cd ${WRKSRC}/src/github.com/gibbonco/titan/cmd/tt; ${SETENV} ${BUILD_ENV} GOPATH=${WRKSRC} go build -o bin/tt

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/github.com/gibbonco/titan/cmd/tt/bin/tt ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
