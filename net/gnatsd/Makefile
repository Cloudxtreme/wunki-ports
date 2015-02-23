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
GH_COMMIT= 	7f26734

USES=		compiler
STRIP=		# stripping can break go binaries

USE_RC_SUBR=	gnatsd
PLIST_FILES=    bin/gnatsd

PORTDOCS=       README.md

OPTIONS_DEFINE= DOCS
DOCS_DESC=      Install gnatsd README file

.include <bsd.port.options.mk>

post-patch:
	@${MKDIR} ${WRKSRC}/src/github.com/apcera
	@ln -s ${WRKSRC} ${WRKSRC}/src/github.com/apcera/gnatsd

do-build:
	@cd ${WRKSRC}/src/github.com/apcera/gnatsd; ${SETENV} ${BUILD_ENV} GOPATH=${WRKSRC} go build -o ${WRKSRC}/bin/${PORTNAME}

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
