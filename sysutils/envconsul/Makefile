PORTNAME=     envconsul
PORTVERSION=  0.5.0
CATEGORIES=   sysutils
MASTER_SITES= https://github.com/hashicorp/envconsul/releases/download/v${PORTVERSION}/
DISTNAME=     ${PORTNAME}_${PORTVERSION}_freebsd_amd64

MAINTAINER= petar@wunki.org
COMMENT=    Read and set environmental variables for processes from Consul
LICENSE=    MPL

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/envconsul ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
