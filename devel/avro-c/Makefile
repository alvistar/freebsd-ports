# Created by: Veniamin Gvozdikov <vg@FreeBSD.org>
# $FreeBSD$

PORTNAME=	avro
PORTVERSION=	1.8.1
PORTREVISION=	1
CATEGORIES=	devel
MASTER_SITES=	APACHE/${PORTNAME}/stable
PKGNAMESUFFIX=	-c
DISTNAME=	${PORTNAME}-src-${PORTVERSION}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Data serialization system for ANSI C

LIB_DEPENDS=	libjansson.so:devel/jansson \
		libsnappy.so:archivers/snappy

BROKEN_aarch64=	Fails to build: error: No atomic implementation
BROKEN_armv6=	Fails to build: error: No atomic implementation
BROKEN_armv7=	Fails to build: error: No atomic implementation
BROKEN_mips=	Fails to build: error: No atomic implementation
BROKEN_mips64=	Fails to build: error: No atomic implementation
BROKEN_sparc64=	Fails to build

USES=		cmake pkgconfig
USE_LDCONFIG=	yes

WRKSRC=		${WRKDIR}/${DISTNAME}/lang/c

post-patch:
	@${REINPLACE_CMD} '/add_subdirectory(docs)/d' \
		${WRKSRC}/CMakeLists.txt
	@${REINPLACE_CMD} 's|/bin/bash|/bin/sh|g' \
		${WRKSRC}/version.sh

.include <bsd.port.mk>
