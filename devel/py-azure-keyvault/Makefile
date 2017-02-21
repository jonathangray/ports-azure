# $OpenBSD$

COMMENT=	Azure KeyVault Client Library for Python

MODPY_EGG_VERSION=	0.1.0
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

RUN_DEPENDS=		devel/py-azure-common

BUILD_DEPENDS=		devel/py-azure-nspkg

post-patch:
	ln -s ${MODPY_SITEPKG}/azure/__init__.py ${WRKSRC}/azure/
	ln -s ${MODPY_SITEPKG}/azure/__init__.pyc ${WRKSRC}/azure/

.include <bsd.port.mk>
