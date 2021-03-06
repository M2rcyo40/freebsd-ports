# $FreeBSD$

PORTNAME=	snack
PORTVERSION=	0.52.17
CATEGORIES=	devel
MASTER_SITES=	https://fedorahosted.org/releases/n/e/newt/
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	newt-${PORTVERSION}

MAINTAINER=	python@FreeBSD.org
COMMENT=	Not Eriks Windowing Toolkit Python bindings

LICENSE=	GPLv2

LIB_DEPENDS=	libslang.so:${PORTSDIR}/devel/libslang2 \
		libpopt.so:${PORTSDIR}/devel/popt \
		libnewt.so:${PORTSDIR}/devel/newt

OPTIONS_DEFINE=	EXAMPLES

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--disable-nls

USES=		python:2
USE_PYTHON=	distutils autoplist
PYSETUP=	${WRKDIR}/setup.py

SUB_FILES=	setup.py
SUB_LIST=	VERSION=${PORTVERSION}

PORTEXAMPLES=	peanuts.py \
		popcorn.py

post-patch: apply-slist
	@${REINPLACE_CMD} -e 's|/usr/bin/python|${PYTHON_CMD}|' \
		${WRKSRC}/popcorn.py \
		${WRKSRC}/peanuts.py

post-install:
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_SCRIPT} ${PORTEXAMPLES:S,^,${WRKSRC}/,} ${STAGEDIR}${EXAMPLESDIR}

.include <bsd.port.mk>
