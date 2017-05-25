# $OpenBSD$

COMMENT=	command line interface for Azure

V=		2.0.6
GH_ACCOUNT=	Azure
GH_PROJECT=	azure-cli
GH_COMMIT=	0b59a2973a7bdc09df7fb7cbe42c25d66ac784f0
DISTNAME=	azure-cli-all-20170509
PKGNAME=	${GH_PROJECT}-${V}

CATEGORIES=	sysutils

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python
MODPY_SETUPUTILS=	Yes

BUILD_DEPENDS=	devel/py-setuptools${MODPY_FLAVOR}
RUN_DEPENDS=	devel/py-adal \
		devel/py-argcomplete \
		devel/py-colorama \
		devel/py-enum34 \
		devel/py-futures \
		devel/py-jmespath \
		devel/py-msrest \
		devel/py-msrestazure>=0.4.7 \
		devel/py-pip \
		devel/py-prompt_toolkit \
		devel/py-six \
		security/py-openssl \
		security/py-paramiko \
		security/py-scp \
		security/py-sshtunnel \
		shells/bash \
		textproc/py-pygments \
		textproc/py-tabulate \
		textproc/py-yaml \
		www/py-requests

# pydocumentdb
# whoosh

RUN_DEPENDS+=\
		devel/py-azure-batch>=1.1.0 \
		devel/py-azure-common \
		devel/py-azure-graphrbac>=0.30.0rc6 \
		devel/py-azure-mgmt \
		devel/py-azure-mgmt-authorization>=0.30.0rc6 \
		devel/py-azure-mgmt-batch>=2.0.0 \
		devel/py-azure-mgmt-compute>=0.33.0 \
		devel/py-azure-mgmt-containerregistry>=0.1.1 \
		devel/py-azure-mgmt-dns>=1.0.0 \
		devel/py-azure-mgmt-documentdb>=0.1.0 \
		devel/py-azure-mgmt-iothub>=0.2.1 \
		devel/py-azure-mgmt-keyvault>=0.30.0 \
		devel/py-azure-mgmt-network>=0.30.0 \
		devel/py-azure-mgmt-nspkg \
		devel/py-azure-mgmt-redis>=1.0.0 \
		devel/py-azure-mgmt-resource>=0.30.2 \
		devel/py-azure-mgmt-sql>=0.2.0 \
		devel/py-azure-mgmt-storage>=0.31.0 \
		devel/py-azure-mgmt-trafficmanager>=0.30.0rc6 \
		devel/py-azure-mgmt-web>=0.31.0 \
		devel/py-azure-multiapi-storage \
		devel/py-azure-nspkg \
		devel/py-azure-servicebus \
		devel/py-azure-servicemanagement-legacy \
		devel/py-azure-storage>=0.33.0

# 	for tests
# py-applicationinsights
# py-nose
# py-mock
# pylint
# vcrpy

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
	azure-cli-batch \
	azure-cli-cdn \
	azure-cli-cloud \
	azure-cli-cognitiveservices \
	azure-cli-component \
	azure-cli-configure \
	azure-cli-cosmosdb \
	azure-cli-dla \
	azure-cli-dls \
	azure-cli-feedback \
	azure-cli-find \
	azure-cli-interactive \
	azure-cli-iot \
	azure-cli-keyvault \
	azure-cli-lab \
	azure-cli-monitor \
	azure-cli-network \
	azure-cli-profile \
	azure-cli-rdbms \
	azure-cli-redis \
	azure-cli-resource \
	azure-cli-role \
	azure-cli-sf \
	azure-cli-sql \
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
