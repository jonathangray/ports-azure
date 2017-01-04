# $OpenBSD$

COMMENT=	Pure python SSH tunnels

MODPY_EGG_VERSION=	0.1.1
DISTNAME=		sshtunnel-${MODPY_EGG_VERSION}
PKGNAME=		py-sshtunnel-${MODPY_EGG_VERSION}

CATEGORIES=	security net

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		security/py-paramiko

.include <bsd.port.mk>
