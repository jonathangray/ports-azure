# $OpenBSD$

COMMENT=	Python wrapper around some of the VSTS APIs

MODPY_EGG_VERSION=	0.118.0
DISTNAME=		vsts-cd-manager-${MODPY_EGG_VERSION}
PKGNAME=		py-vsts-cd-manager-${MODPY_EGG_VERSION}

HOMEPAGE=		https://github.com/microsoft/vsts-cd-manager

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-mock \
			devel/py-msrest

.include <bsd.port.mk>
