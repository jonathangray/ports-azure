# $OpenBSD$

COMMENT=	Azure Compute Resource Management Client Library for Python

MODPY_EGG_VERSION=	0.32.1
DISTNAME=		azure-mgmt-compute-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-mgmt-compute-${MODPY_EGG_VERSION}
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
