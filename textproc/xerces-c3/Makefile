# Created by: gahr
# $FreeBSD$

PORTNAME=	xerces-c
PORTVERSION=	3.1.2
CATEGORIES=	textproc
MASTER_SITES=	APACHE/xerces/c/3/sources
PKGNAMESUFFIX=	3

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Validating XML parser from the Apache XML Project

LICENSE=	APACHE20

CONFLICTS_INSTALL=	xerces-c2-[0-9]* xerces-c2-devel-[0-9]*

CONFIGURE_ARGS=	--enable-netaccessor-socket \
		--enable-transcoder-iconv \
		--with-pkgconfigdir=${PREFIX}/libdata/pkgconfig
GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip
MAKE_ENV=	XERCESCROOT=${WRKSRC}
TEST_TARGET=	check
USE_LDCONFIG=	yes
USES=		cpe gmake libtool pathfix

PLIST_SUB=	MAJOR_VER=${PORTVERSION:R}

CPE_PRODUCT=	xerces-c++
CPE_VENDOR=	apache

post-install:
	${LN} -s libxerces-c-${PORTVERSION:R}.so ${STAGEDIR}${PREFIX}/lib/libxerces-c.so.${PORTVERSION:R:R}

.include <bsd.port.mk>
