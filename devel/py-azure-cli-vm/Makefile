# $OpenBSD$

COMMENT=	Azure Command-Line Tools VM Command Module

MODPY_EGG_VERSION=	0.1.0b11
DISTNAME=		azure-cli-vm-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-cli-vm-${MODPY_EGG_VERSION}

HOMEPAGE=		https://github.com/Azure/azure-cli

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-azure-cli-core \
			devel/py-azure-mgmt-compute \
			devel/py-azure-mgmt-network \
			devel/py-azure-mgmt-resource \
			devel/py-azure-storage \
			devel/py-futures \
			security/py-paramiko

.include <bsd.port.mk>
