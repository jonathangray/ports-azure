# $OpenBSD$

COMMENT=	Azure Command-Line Tools ACS Command Module

MODPY_EGG_VERSION=	0.1.0b11
DISTNAME=		azure-cli-acs-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-cli-acs-${MODPY_EGG_VERSION}

HOMEPAGE=		https://github.com/Azure/azure-cli

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-azure-mgmt-compute \
			devel/py-six \
			security/py-scp \
			security/py-sshtunnel \
			security/py-paramiko \
			textproc/py-yaml

.include <bsd.port.mk>
