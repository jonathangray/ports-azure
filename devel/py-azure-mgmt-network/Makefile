# $OpenBSD$

COMMENT=	Azure Network Resource Management Client Library

MODPY_EGG_VERSION=	1.0.0
DISTNAME=		azure-mgmt-network-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-mgmt-network-${MODPY_EGG_VERSION}
EXTRACT_SUFX=		.zip

HOMEPAGE=		https://github.com/Azure/azure-sdk-for-python

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-azure-mgmt-nspkg \
			devel/py-azure-common

.include <bsd.port.mk>
