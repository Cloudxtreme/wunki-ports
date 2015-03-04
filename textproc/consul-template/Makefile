PORTNAME=     consul-template
PORTVERSION=  0.7.0
CATEGORIES=   textproc
MASTER_SITES= https://github.com/hashicorp/consul-template/releases/download/v${PORTVERSION}/
DISTNAME=     ${PORTNAME}_${PORTVERSION}_freebsd_amd64

MAINTAINER= petar@wunki.org
COMMENT=    Generic template rendering and notifications with Consul
LICENSE=    MPL

USE_RC_SUBR=	consul_template

do-build:
	:

do-install:
	ls -la ${WRKSRC}
	${INSTALL_PROGRAM} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
