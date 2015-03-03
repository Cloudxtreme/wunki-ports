PORTNAME=	envconsul
PORTVERSION=	0.5.0
CATEGORIES=	sysutils
MASTER_SITES=	https://github.com/hashicorp/envconsul/releases/download/v${PORTVERSION}/
DISTFILES= envconsul_${PORTVERSION}_freebsd_amd64.tar.gz

MAINTAINER=	petar@wunki.org
COMMENT=	  Read and set environmental variables for processes from Consul
LICENSE=	  MPL

WRKSRC= 	  ${WRKDIR}/${PORTNAME}_${PORTVERSION}_freebsd_amd64

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/envconsul ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
