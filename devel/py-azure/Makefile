# $OpenBSD$

COMMENT=	Azure Client Libraries for Python

MODPY_EGG_VERSION=	2.0.0rc6
DISTNAME=		azure-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-${MODPY_EGG_VERSION}
EXTRACT_SUFX=		.zip

HOMEPAGE=		https://github.com/Azure/azure-sdk-for-python

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-azure-mgmt \
			devel/py-azure-servicebus \
			devel/py-azure-storage \
			devel/py-azure-servicemanagement-legacy

#			devel/py-azure-batch \

.include <bsd.port.mk>
