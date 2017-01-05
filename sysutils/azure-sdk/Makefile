# $OpenBSD$

COMMENT=	Azure SDK for Python

# snapshot for azure-mgmt-containerregistry
V=		20170105
GH_ACCOUNT=	Azure
GH_PROJECT=	azure-sdk-for-python
GH_TAGNAME=	
GH_COMMIT=	2f86e7ec014f9f9030b9e860e21ea689615c09ed
PKGNAME=	azure-sdk-${V}
DISTNAME=	${GH_PROJECT}-${V}

CATEGORIES=	sysutils

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

RUN_DEPENDS=	devel/py-azure-storage

PYMODS= \
		azure-batch \
		azure-common \
		azure-graphrbac \
		azure-mgmt \
		azure-mgmt-authorization \
		azure-mgmt-compute \
		azure-mgmt-containerregistry \
		azure-mgmt-dns \
		azure-mgmt-network \
		azure-mgmt-nspkg \
		azure-mgmt-storage \
		azure-mgmt-trafficmanager \
		azure-mgmt-web \
		azure-nspkg \
		azure-servicebus \
		azure-servicemanagement-legacy

# azure-mgmt-resource 0.30.2 removes a file used by azure-cli-resource
# 0.31.0 must be used
#		azure-mgmt-resource 

do-build:

do-install:
	${INSTALL_DATA_DIR} ${WRKINST}${MODPY_SITEPKG}
.for PYMOD in ${PYMODS}
	cd ${WRKSRC}/${PYMOD} ; \
	pax -rw -pa \
	    `find . -name '*.py' '!' '(' -path './setup.py' ')' -print` \
	    ${WRKINST}${MODPY_SITEPKG}
.endfor
	${MODPY_BIN} ${MODPY_LIBDIR}/compileall.py ${WRKINST}${MODPY_SITEPKG}

.include <bsd.port.mk>
