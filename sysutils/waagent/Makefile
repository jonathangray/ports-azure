# $OpenBSD$

COMMENT=		Microsoft Azure Linux Agent

V=			2.2.12
GH_ACCOUNT=		Azure
GH_PROJECT=		WALinuxAgent
GH_COMMIT=		ed7a7b788869102ce8398259ce7f756cbc43a868
DISTNAME=		waagent-all-20170531
PKGNAME=		waagent-${V}

CATEGORIES=		sysutils

# Apache 2.0
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python
MODPY_SETUPTOOLS=	Yes

MODPY_ADJ_FILES=	bin/waagent

RUN_DEPENDS=		security/openssl

NO_TEST=		Yes

post-install:
	rm -f ${WRKINST}/${PREFIX}/lib/\
		python${MODPY_VERSION}/site-packages/__main__.{py,pyc}
	rm -f ${PREFIX}/sbin/waagent2.0
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/waagent
	mv ${WRKINST}/etc/waagent.conf \
		${PREFIX}/share/examples/waagent/waagent.conf

.include <bsd.port.mk>
