PORTNAME=		gnatsd
PORTVERSION=	0.5.6
CATEGORIES=		sysutils
MAINTAINER=		petar@wunki.org
COMMENT=		High Performance NATS Server

LICENSE=		MIT

BUILD_DEPENDS=	${LOCALBASE}/bin/go:${PORTSDIR}/lang/go

USE_GITHUB=	yes
GH_ACCOUNT=	apcera
GH_TAGNAME=	v${PORTVERSION}
GH_COMMIT= 	62c5c4d

USES=		compiler
STRIP=		# stripping can break go binaries

PLIST_FILES=    gnatsd

PORTDOCS=       README.md

OPTIONS_DEFINE= DOCS
DOCS_DESC=      Install gnatsd README file

.include <bsd.port.options.mk>

post-patch:
	@${MKDIR} ${WRKSRC}/src/github.com/apcera
	ls -la ${WRKDIR}
	ls -la ${WRKSRC}
	@ln -s ${WRKSRC} ${WRKSRC}/src/github.com/appcera/gnatsd

do-build:
	@cd ${WRKSRC}/src/github.com/appcera/gnatsd; ${SETENV} ${BUILD_ENV} GOPATH=${WRKSRC} go build -o bin/gnatsd

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/gnatsd ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
