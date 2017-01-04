# $OpenBSD$

COMMENT=	command line interface for Azure

MODPY_EGG_VERSION=	0.1.0b10
DISTNAME=		azure-cli-${MODPY_EGG_VERSION}

HOMEPAGE=		https://github.com/Azure/azure-cli

CATEGORIES=	sysutils

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-azure-cli-core>=${MODPY_EGG_VERSION} \
			devel/py-azure-cli-acr \
			devel/py-azure-cli-acs \
			devel/py-azure-cli-appservice \
			devel/py-azure-cli-cloud \
			devel/py-azure-cli-component \
			devel/py-azure-cli-configure \
			devel/py-azure-cli-container \
			devel/py-azure-cli-context \
			devel/py-azure-cli-feedback \
			devel/py-azure-cli-network \
			devel/py-azure-cli-profile \
			devel/py-azure-cli-resource \
			devel/py-azure-cli-role \
			devel/py-azure-cli-storage \
			devel/py-azure-cli-taskhelp \
			devel/py-azure-cli-vm

post-extract:
	sed -i -e 's,/bin/bash,${LOCALBASE}/bin/bash,' ${WRKSRC}/az
	sed -i -e "s,^python,${MODPY_BIN}," ${WRKSRC}/az

.include <bsd.port.mk>
