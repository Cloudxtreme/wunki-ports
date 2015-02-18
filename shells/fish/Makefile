# Created by: Kai Wang <kaiw27@gmail.com>
# $FreeBSD: head/shells/fish/Makefile 374430 2014-12-09 21:30:14Z jgh $

PORTNAME=	fish
PORTVERSION=	2.1.2
CATEGORIES=	shells
MASTER_SITES= https://github.com/fish-shell/fish-shell/archive/
DISTFILES= ${PORTVERSION}.tar.gz
DISTNAME= fish-shell-${PORTVERSION}

MAINTAINER=	freebsd.users@gmail.com
COMMENT=	User friendly command line shell

LICENSE=	GPLv2

USES=		gmake iconv
USE_AUTOTOOLS=	autoconf

CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib -pthread ${ICONV_LIB}

OPTIONS_DEFINE=	NLS
OPTIONS_SUB=	yes

NLS_USES=		gettext
NLS_CONFIGURE_ENV=	ac_cv_func_gettext=yes
NLS_CONFIGURE_OFF=	--without-gettext

post-install:
.for i in fish fish_indent fish_pager fishd mimedb
	@${STRIP_CMD} ${STAGEDIR}${PREFIX}/bin/${i}
.endfor

.include <bsd.port.mk>
