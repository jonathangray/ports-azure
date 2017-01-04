# $OpenBSD$

COMMENT=	AutoRest: Python Client Runtime - Azure Module

MODPY_EGG_VERSION=	0.4.6
DISTNAME=		msrestazure-${MODPY_EGG_VERSION}
PKGNAME=		py-msrestazure-${MODPY_EGG_VERSION}
EXTRACT_SUFX=		.zip

HOMEPAGE=		https://github.com/Azure/msrestazure-for-python

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-adal \
			devel/py-msrest \
			security/py-keyring

.include <bsd.port.mk>
