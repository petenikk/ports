COMMENT =	portable, lightweight framework for the Objective-C language

DISTNAME =	objfw-1.0.3

SHARED_LIBS +=	objfw		0.0
SHARED_LIBS +=	objfwrt		0.0
SHARED_LIBS +=	objfwtls	0.0

CATEGORIES =	devel

HOMEPAGE =	https://objfw.nil.im/

MAINTAINER =	Jonathan Schleifer <js@nil.im>

# GPLv2 or GPLv3 or QPL
PERMIT_PACKAGE =	Yes

# uses pledge()
WANTLIB =		c c++abi crypto m pthread ssl

SITES =			https://objfw.nil.im/downloads/

COMPILER=		base-clang ports-clang

CONFIGURE_STYLE =	gnu
CONFIGURE_FLAGS +=	--disable-silent-rules

MAKE_FLAGS +=	OBJFW_LIB_MAJOR=${LIBobjfw_VERSION:R}
MAKE_FLAGS +=	OBJFW_LIB_MINOR=${LIBobjfw_VERSION:E}
MAKE_FLAGS +=	OBJFWRT_LIB_MAJOR=${LIBobjfwrt_VERSION:R}
MAKE_FLAGS +=	OBJFWRT_LIB_MINOR=${LIBobjfwrt_VERSION:E}
MAKE_FLAGS +=	OBJFWTLS_LIB_MAJOR=${LIBobjfwtls_VERSION:R}
MAKE_FLAGS +=	OBJFWTLS_LIB_MINOR=${LIBobjfwtls_VERSION:E}

.include <bsd.port.mk>
