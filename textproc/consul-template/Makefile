PORTNAME=     consul-template
PORTVERSION=  0.7.0
CATEGORIES=   sysutils
MASTER_SITES= https://github.com/hashicorp/consul-template/releases/download/v${PORTVERSION}/
DISTNAME=     ${PORTNAME}_${PORTVERSION}_freebsd_amd64

MAINTAINER= petar@wunki.org
COMMENT=    Generic template rendering and notifications with Consul
LICENSE=    MPL

do-build:
	:

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
