# $OpenBSD$

COMMENT=	scp module for paramiko

MODPY_EGG_VERSION=	0.10.2
DISTNAME=		scp-${MODPY_EGG_VERSION}
PKGNAME=		py-scp-${MODPY_EGG_VERSION}

CATEGORIES=	security net

# LGPL 2.1
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		security/py-paramiko

.include <bsd.port.mk>
