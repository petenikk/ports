COMMENT =	graphics library providing basic drawing primitives
CATEGORIES =	graphics

V =		5.0.0
REVISION =	4
DISTNAME =	graphics-$V
PKGNAME =	ocaml-graphics-$V

# LGPL 2.1 with linking exception
PERMIT_PACKAGE = Yes

WANTLIB +=	X11

SITES =		https://github.com/ocaml/graphics/releases/download/${V}/
EXTRACT_SUFX =	.tbz

MODULES =	lang/ocaml

BUILD_DEPENDS = devel/dune

MAKE_ENV =	CPATH=${X11BASE}/include \
		LIBRARY_PATH=${X11BASE}/lib

ALL_TARGET =	default

post-install:
	mv ${PREFIX}/share/doc/graphics ${PREFIX}/share/doc/ocaml-graphics

.include <bsd.port.mk>
