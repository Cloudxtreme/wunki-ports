PORTNAME= titan
DISTVERSION= 0.0.1-62
PORTVERSION= 1

CATEGORIES= 	www
MASTER_SITES= https://s3.amazonaws.com/gibbon-deployment/

MAINTAINER= petar@wunki.org
COMMENT=    Central API for Gibbon

LICENSE=  	MPL

BUILD_DEPENDS=  ${LOCALBASE}/bin/go:${PORTSDIR}/lang/go
RUN_DEPENDS= 		${LOCALBASE}/bin/envconsul:${PORTSDIR}/sysutils/envconsul

USES=   compiler
STRIP=  # stripping can break go binaries

PLIST_FILES= bin/titan

post-patch:
	${MKDIR} ${WRKSRC}/src/github.com/gibbonco
	@ln -s ${WRKSRC} ${WRKSRC}/src/github.com/gibbonco/titan

do-build:
	@cd ${WRKSRC}/src/github.com/gibbonco/titan; ${SETENV} ${BUILD_ENV} GOPATH=${WRKSRC} go build -o bin/titan

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/github.com/gibbonco/titan/bin/titan ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
