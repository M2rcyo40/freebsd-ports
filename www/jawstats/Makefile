# Created by: Alan Snelson <alan@wave2.org>
# $FreeBSD$

PORTNAME=	jawstats
DISTVERSION=	0.7beta
CATEGORIES=	www
MASTER_SITES=	http://www.jawstats.com/src/

MAINTAINER=	Alan@Wave2.org
COMMENT=	JAWStats is a Free Web Site Statistics tool

RUN_DEPENDS=	awstats>=6.8:${PORTSDIR}/www/awstats

NO_WRKSUBDIR=	yes
NO_BUILD=	yes
USE_PHP=	yes
WANT_PHP_WEB=	yes
DEFAULT_PHP_VER=	5
SUB_FILES=	pkg-message

do-install:
	@${MKDIR} ${STAGEDIR}/${WWWDIR}
	@cd ${WRKSRC}; ${COPYTREE_SHARE} . ${STAGEDIR}/${WWWDIR}

.include <bsd.port.mk>
