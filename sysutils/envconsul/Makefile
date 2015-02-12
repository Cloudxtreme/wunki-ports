PORTNAME=	envconsul
PORTVERSION=	0.4.0
CATEGORIES=	sysutils
MASTER_SITES=	https://github.com/${GH_ACCOUNT}/${GH_PROJECT}/archive/${GH_TAGNAME}.tar.gz?dummy=/:group1 \
		https://github.com/hashicorp/consul-template/archive/d0dcc195fbf75cb71feb5337df89a9627cda58d1.tar.gz?dummy=/:group2 \
		https://github.com/hashicorp/hcl/archive/e51eabcdf801f663738fa12f4340fbad13062738.tar.gz?dummy=/:group3 \
		https://github.com/hashicorp/consul/archive/17d1c392e45ecf68af4755ed66989f01d4e9edbe.tar.gz?dummy=/:group4 \
		https://github.com/hashicorp/logutils/archive/23b0af5510a2d1442103ef83ffcf53eb82f3debc.tar.gz?dummy=/:group5 \
		https://github.com/hashicorp/terraform/archive/4e11ed4327fa638a4c2587489a8660c69beb4047.tar.gz?dummy=/:group6 \
		https://github.com/mitchellh/mapstructure/archive/740c764bc6149d3f1806231418adb9f52c11bcbf.tar.gz?dummy=/:group7
DISTFILES=	envconsul-0.4.0.tar.gz:group1 \
		hashicorp_consul-template_d0dcc195fbf75cb71feb5337df89a9627cda58d1.tar.gz:group2 \
		hashicorp_hcl_e51eabcdf801f663738fa12f4340fbad13062738.tar.gz:group3 \
		hashicorp_consul_17d1c392e45ecf68af4755ed66989f01d4e9edbe.tar.gz:group4 \
		hashicorp_logutils_23b0af5510a2d1442103ef83ffcf53eb82f3debc.tar.gz:group5 \
		hashicorp_terraform_4e11ed4327fa638a4c2587489a8660c69beb4047.tar.gz:group6 \
		mitchellh_mapstructure_740c764bc6149d3f1806231418adb9f52c11bcbf.tar.gz:group7 

MAINTAINER=	petar@wunki.org
COMMENT=	Read and set environmental variables for processes from Consul

LICENSE=	MPL

BUILD_DEPENDS=	${LOCALBASE}/bin/go:${PORTSDIR}/lang/go

USES=		compiler

USE_GITHUB=	yes
GH_ACCOUNT=	hashicorp
GH_COMMIT=	70b145b
GH_TAGNAME=	v${PORTVERSION}

STRIP=		# stripping can break go binaries

post-patch:
	${MKDIR} ${WRKSRC}/src/github.com/hashicorp/envconsul
.for src in .gitignore .travis.yml CHANGELOG.md LICENSE Makefile README.md \
	cli.go config.go main.go runner.go
	@${MV} ${WRKSRC}/${src} \
		${WRKSRC}/src/github.com/hashicorp/envconsul
.endfor
	@${MKDIR} ${WRKSRC}/src/github.com/armon
	@${MKDIR} ${WRKSRC}/src/github.com/mitchellh
	@${MV} ${WRKDIR}/consul-template-d0dcc195fbf75cb71feb5337df89a9627cda58d1 \
		${WRKSRC}/src/github.com/hashicorp/consul-template
	@${MV} ${WRKDIR}/consul-17d1c392e45ecf68af4755ed66989f01d4e9edbe \
		${WRKSRC}/src/github.com/hashicorp/consul
	@${MV} ${WRKDIR}/hcl-e51eabcdf801f663738fa12f4340fbad13062738 \
		${WRKSRC}/src/github.com/hashicorp/hcl
	@${MV} ${WRKDIR}/logutils-23b0af5510a2d1442103ef83ffcf53eb82f3debc \
		${WRKSRC}/src/github.com/hashicorp/logutils
	@${MV} ${WRKDIR}/terraform-4e11ed4327fa638a4c2587489a8660c69beb4047 \
		${WRKSRC}/src/github.com/hashicorp/terraform
	@${MV} ${WRKDIR}/mapstructure-740c764bc6149d3f1806231418adb9f52c11bcbf \
		${WRKSRC}/src/github.com/mitchellh/mapstructure

do-build:
	@cd ${WRKSRC}/src/github.com/hashicorp/envconsul; ${SETENV} ${BUILD_ENV} GOPATH=${WRKSRC} go build -o bin/envconsul

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/src/github.com/hashicorp/envconsul/bin/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/

.include <bsd.port.mk>
