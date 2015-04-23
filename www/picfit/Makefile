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

GO_PKGNAME= github.com/${GH_ACCOUNT}/${GH_PROJECT}

.include <bsd.port.options.mk>

.include "${PORTSDIR}/lang/go/files/bsd.go.mk"
.include <bsd.port.mk>
