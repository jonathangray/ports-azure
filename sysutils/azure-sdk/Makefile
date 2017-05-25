# $OpenBSD$

COMMENT=	Azure SDK for Python

V=		2.0.0
GH_ACCOUNT=	Azure
GH_PROJECT=	azure-sdk-for-python
GH_TAGNAME=	azure_2.0.0
PKGNAME=	azure-sdk-${V}
DISTNAME=	${GH_PROJECT}-${V}

CATEGORIES=	sysutils

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=	devel/py-azure-storage

.include <bsd.port.mk>
