# $OpenBSD$

COMMENT=	Azure Command-Line Tools ACR Command Module

MODPY_EGG_VERSION=	0.1.0b10
DISTNAME=		azure-cli-acr-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-cli-acr-${MODPY_EGG_VERSION}

HOMEPAGE=		https://github.com/Azure/azure-cli

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-azure-cli-core \
			devel/py-azure-mgmt-resource \
			devel/py-azure-mgmt-storage \
			devel/py-azure-mgmt-containerregistry

.include <bsd.port.mk>
