# $OpenBSD$

COMMENT=	Azure DocumentDB Management Client Library for Python

MODPY_EGG_VERSION=	0.1.3
DISTNAME=		azure-mgmt-documentdb-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-mgmt-documentdb-${MODPY_EGG_VERSION}
EXTRACT_SUFX=		.zip

HOMEPAGE=		https://github.com/Azure/azure-sdk-for-python

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-azure-common \
			devel/py-azure-mgmt-nspkg

BUILD_DEPENDS=		devel/py-azure-nspkg \
			devel/py-azure-mgmt-nspkg

.include <bsd.port.mk>
