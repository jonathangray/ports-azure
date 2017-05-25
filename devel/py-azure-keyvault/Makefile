# $OpenBSD$

COMMENT=	Azure KeyVault Client Library for Python

MODPY_EGG_VERSION=	0.2.0
DISTNAME=		azure-keyvault-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-keyvault-${MODPY_EGG_VERSION}
EXTRACT_SUFX=		.zip

HOMEPAGE=		https://github.com/Azure/azure-sdk-for-python

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		sysutils/azure-sdk
BUILD_DEPENDS=		sysutils/azure-sdk

.include <bsd.port.mk>
