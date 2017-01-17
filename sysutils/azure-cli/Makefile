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
MODPY_SETUPUTILS=	Yes

RUN_DEPENDS=	devel/py-adal \
		devel/py-argcomplete \
		devel/py-colorama \
		devel/py-enum34 \
		devel/py-jmespath \
		devel/py-msrest \
		devel/py-msrestazure \
		devel/py-pip \
		devel/py-six \
		security/py-paramiko \
		security/py-scp \
		security/py-sshtunnel \
		shells/bash \
		textproc/py-pygments \
		textproc/py-tabulate \
		textproc/py-yaml \
		www/py-requests

RUN_DEPENDS+=\
		devel/py-azure-batch \
		devel/py-azure-common \
		devel/py-azure-graphrbac \
		devel/py-azure-mgmt \
		devel/py-azure-mgmt-authorization \
		devel/py-azure-mgmt-compute \
		devel/py-azure-mgmt-containerregistry \
		devel/py-azure-mgmt-dns \
		devel/py-azure-mgmt-network \
		devel/py-azure-mgmt-nspkg \
		devel/py-azure-mgmt-resource \
		devel/py-azure-mgmt-storage \
		devel/py-azure-mgmt-trafficmanager \
		devel/py-azure-mgmt-web \
		devel/py-azure-nspkg \
		devel/py-azure-servicebus \
		devel/py-azure-servicemanagement-legacy \
		devel/py-azure-storage

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
	    ${WRKINST}${MODPY_SITEPKG} ; \
	${MODPY_BIN} ./${MODPY_SETUP} ${MODPY_DISTUTILS_INSTALL}
.endfor
.for CMOD in ${CMODS}
	cd ${WRKSRC}/src/command_modules/${CMOD} ; \
	pax -rw -pa \
	    `find . -name '*.py' '!' '(' -path './setup.py' ')' -print` \
	    ${WRKINST}${MODPY_SITEPKG} ; \
	${MODPY_BIN} ./${MODPY_SETUP} ${MODPY_DISTUTILS_INSTALL}
.endfor
	rm -f ${PREFIX}/bin/az{,.bat,.completion.sh}
	${INSTALL_SCRIPT} ${WRKSRC}/src/azure-cli/az ${PREFIX}/bin/az
	${MODPY_BIN} ${MODPY_LIBDIR}/compileall.py ${WRKINST}${MODPY_SITEPKG}
	rm -f ${WRKINST}${MODPY_SITEPKG}/azure/__init__.{py,pyc}

.include <bsd.port.mk>
