# $OpenBSD$

COMMENT=	command line interface for Azure

V=		0.1.0b11
GH_ACCOUNT=	Azure
GH_PROJECT=	azure-cli
GH_TAGNAME=	all-v${V}
PKGNAME=	${GH_PROJECT}-${V}

CATEGORIES=	sysutils

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

RUN_DEPENDS=		sysutils/azure-sdk


RUN_DEPENDS=		devel/py-adal \
			devel/py-argcomplete \
			devel/py-azure-mgmt-resource \
			devel/py-colorama \
			devel/py-enum34 \
			devel/py-jmespath \
			devel/py-msrest \
			devel/py-msrestazure \
			devel/py-pip \
			devel/py-six \
			sysutils/azure-sdk \
			textproc/py-pygments \
			textproc/py-tabulate \
			textproc/py-yaml \
			www/py-requests
# applicationinsights

do-build:

post-extract:
	sed -i -e 's,/bin/bash,${LOCALBASE}/bin/bash,' ${WRKSRC}/src/azure-cli/az
	sed -i -e "s,^python,${MODPY_BIN}," ${WRKSRC}/src/azure-cli/az

PYMODS=\
		azure-cli \
		azure-cli-core \
		azure-cli-nspkg
CMODS=\
		azure-cli-acr \
		azure-cli-acs \
		azure-cli-appservice \
		azure-cli-cloud \
		azure-cli-component \
		azure-cli-configure \
		azure-cli-container \
		azure-cli-context \
		azure-cli-feedback \
		azure-cli-network \
		azure-cli-profile \
		azure-cli-resource \
		azure-cli-role \
		azure-cli-storage \
		azure-cli-taskhelp \
		azure-cli-vm

do-install:
	${INSTALL_DATA_DIR} ${WRKINST}${MODPY_SITEPKG}
.for PYMOD in ${PYMODS}
	cd ${WRKSRC}/src/${PYMOD} ; \
	pax -rw -pa \
	    `find . -name '*.py' '!' '(' -path './setup.py' ')' -print` \
	    ${WRKINST}${MODPY_SITEPKG}
.endfor
.for CMOD in ${CMODS}
	cd ${WRKSRC}/src/command_modules/${CMOD} ; \
	pax -rw -pa \
	    `find . -name '*.py' '!' '(' -path './setup.py' ')' -print` \
	    ${WRKINST}${MODPY_SITEPKG}
.endfor
	${INSTALL_SCRIPT} ${WRKSRC}/src/azure-cli/az ${PREFIX}/bin/az
	${MODPY_BIN} ${MODPY_LIBDIR}/compileall.py ${WRKINST}${MODPY_SITEPKG}

.include <bsd.port.mk>
