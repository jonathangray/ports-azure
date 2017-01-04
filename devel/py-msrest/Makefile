# $OpenBSD$

COMMENT=	AutoRest swagger generator Python client runtime

MODPY_EGG_VERSION=	0.4.4
DISTNAME=		msrest-${MODPY_EGG_VERSION}
PKGNAME=		py-msrest-${MODPY_EGG_VERSION}
EXTRACT_SUFX=		.zip

HOMEPAGE=		https://github.com/Azure/autorest

CATEGORIES=	devel

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI=		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-certifi \
			devel/py-enum34 \
			devel/py-isodate \
			textproc/py-chardet \
			www/py-requests \
			www/py-requests-oauthlib

.include <bsd.port.mk>
