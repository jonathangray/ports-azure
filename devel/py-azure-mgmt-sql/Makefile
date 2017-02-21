# $OpenBSD$

COMMENT=	Azure SQL Management Client Library for Python

MODPY_EGG_VERSION=	0.2.0
DISTNAME=		azure-mgmt-sql-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-mgmt-sql-${MODPY_EGG_VERSION}
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

post-patch:
	ln -s ${MODPY_SITEPKG}/azure/__init__.py ${WRKSRC}/azure/
	ln -s ${MODPY_SITEPKG}/azure/__init__.pyc ${WRKSRC}/azure/
	ln -s ${MODPY_SITEPKG}/azure/mgmt/__init__.py ${WRKSRC}/azure/mgmt/
	ln -s ${MODPY_SITEPKG}/azure/mgmt/__init__.pyc ${WRKSRC}/azure/mgmt/

.include <bsd.port.mk>
