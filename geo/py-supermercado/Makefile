COMMENT =	mercantile additional commands

MODPY_EGG_VERSION =	0.2.0
DISTNAME =	supermercado-${MODPY_EGG_VERSION}
PKGNAME =	py-${DISTNAME}
REVISION =	2

CATEGORIES =	geo
MAINTAINER =    Martin Reindl <martin@catai.org>

# BSD
PERMIT_PACKAGE =	Yes

MODULES =	lang/python

FLAVORS =	python3
FLAVOR =	python3

MODPY_PYBUILD =	setuptools
MODPY_PI =	Yes

RUN_DEPENDS =	math/py-affine${MODPY_FLAVOR} \
		devel/py-click${MODPY_FLAVOR} \
		devel/py-click-plugins${MODPY_FLAVOR} \
		geo/py-cligj${MODPY_FLAVOR} \
		geo/py-mercantile${MODPY_FLAVOR} \
		math/py-numpy${MODPY_FLAVOR} \
		geo/py-rasterio${MODPY_FLAVOR}

# does not package tests, only available via git
NO_TEST =       Yes
TEST_DEPENDS =	devel/py-test${MODPY_FLAVOR}

.include <bsd.port.mk>
