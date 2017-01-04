# $OpenBSD$

COMMENT=	Azure Command-Line Tools Feedback Command Module

MODPY_EGG_VERSION=	0.1.0b10
DISTNAME=		azure-cli-feedback-${MODPY_EGG_VERSION}
PKGNAME=		py-azure-cli-feedback-${MODPY_EGG_VERSION}

HOMEPAGE=		https://github.com/Azure/azure-cli

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-azure-cli-core
# applicationinsights

.include <bsd.port.mk>
