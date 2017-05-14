# $OpenBSD$

COMMENT=		Microsoft Azure Linux Agent

V=			2.2.11
GH_ACCOUNT=		reyk
GH_PROJECT=		WALinuxAgent
GH_COMMIT=		213d53cf6478adc063d8f0eb9f1a8bdf60ea1043
DISTNAME=		waagent-all-20170513
PKGNAME=		waagent-${V}

CATEGORIES=		sysutils

# Apache 2.0
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		security/openssl

NO_TEST=		Yes

post-extract:
	sed -i -e "s,^#!/usr/bin/env python,#!${MODPY_BIN}," \
		${WRKSRC}/bin/waagent

post-install:
	rm -f ${WRKINST}/${PREFIX}/lib/\
		python${MODPY_VERSION}/site-packages/__main__.{py,pyc}
	rm -f ${PREFIX}/sbin/waagent2.0
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/waagent
	mv ${WRKINST}/etc/waagent.conf \
		${PREFIX}/share/examples/waagent/waagent.conf

.include <bsd.port.mk>
