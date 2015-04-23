PORTNAME=			picfit
PORTVERSION=	0.2
CATEGORIES=		www
MAINTAINER=		petar@wunki.org
COMMENT=			Picture thumbnailing

LICENSE=			MIT

BUILD_DEPENDS=	${LOCALBASE}/bin/go:${PORTSDIR}/lang/go

USE_GITHUB=	yes
GH_ACCOUNT=	wunki
GH_COMMIT= 089549a

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
	${MKDIR} ${WRKSRC}/src/github.com/wunki
	@ln -s ${WRKSRC} ${WRKSRC}/src/github.com/wunki/picfit

do-build:
	@cd ${WRKSRC}/src/github.com/wunki/picfit; ${SETENV} ${BUILD_ENV} GOPATH=${WRKSRC} go build -o bin/picfit

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/github.com/gibbonco/janus/bin/janus ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>

