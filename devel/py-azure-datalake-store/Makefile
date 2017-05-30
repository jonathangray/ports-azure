# $OpenBSD$

COMMENT=	Azure Data Lake Store Filesystem Client Library for Python

MODPY_EGG_VERSION=	0.0.9
DISTNAME=		azure-datalake-store-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-datalake-store-${MODPY_EGG_VERSION}

HOMEPAGE=		https://github.com/Azure/azure-data-lake-store-python

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-adal \
			devel/py-cffi \
			devel/py-futures \
			devel/py-msrest \
			devel/py-pathlib2

.include <bsd.port.mk>
