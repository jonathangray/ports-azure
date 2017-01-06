# $OpenBSD$

COMMENT=	Azure Active Directory Library

MODPY_EGG_VERSION=	0.4.3
DISTNAME=		adal-${MODPY_EGG_VERSION}
PKGNAME=		py-adal-${MODPY_EGG_VERSION}

HOMEPAGE=		https://github.com/AzureAD/azure-activedirectory-library-for-python

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-dateutil \
			security/py-cryptography \
			www/py-jwt \
			www/py-requests

.include <bsd.port.mk>
