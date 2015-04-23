PORTNAME=			picfit
PORTVERSION=	0.2
CATEGORIES=		www
MAINTAINER=		petar@wunki.org
COMMENT=			Picture thumbnailing

LICENSE=			MIT

BUILD_DEPENDS=	${LOCALBASE}/bin/go:${PORTSDIR}/lang/go

USE_GITHUB=	yes
GH_ACCOUNT=	thoas
GH_TAGNAME=	${PORTVERSION}
GH_COMMIT= 	490dadb

USES=		compiler
STRIP=		# stripping can break go binaries

PLIST_FILES=    bin/picfit

USE_RC_SUBR=	picfit
USERS=			picfit
GROUPS=			picfit

PORTDOCS=       README.md

OPTIONS_DEFINE= DOCS
DOCS_DESC=      Install picfit README file

.include <bsd.port.options.mk>

post-patch:
	@${MKDIR} ${WRKSRC}/src/github.com/thoas
	@ln -s ${WRKSRC} ${WRKSRC}/src/github.com/thoas/picfit

do-build:
	@${SETENV} ${BUILD_ENV} GOPATH=${WRKSRC}; go get github.com/tools/godep; godep restore;
	@cd ${WRKSRC}/src/github.com/thoas/picfit; ${SETENV} ${BUILD_ENV} GOPATH=${WRKSRC} go build -o ${WRKSRC}/bin/${PORTNAME}

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
