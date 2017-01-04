# $OpenBSD$

COMMENT=	Azure Command-Line Tools Core Module

MODPY_EGG_VERSION=	0.1.0b10
DISTNAME=		azure-cli-core-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-cli-core-${MODPY_EGG_VERSION}

HOMEPAGE=		https://github.com/Azure/azure-cli

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-adal \
			devel/py-argcomplete \
			devel/py-azure-mgmt-trafficmanager \
			devel/py-azure-mgmt-dns \
			devel/py-colorama \
			devel/py-enum34 \
			devel/py-jmespath \
			devel/py-msrest \
			devel/py-msrestazure \
			devel/py-pip \
			devel/py-six \
			textproc/py-pygments \
			textproc/py-tabulate \
			textproc/py-yaml \
			www/py-requests
# applicationinsights

.include <bsd.port.mk>
