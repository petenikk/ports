COMMENT=	Python interface to the OpenSSL library

MODPY_EGG_VERSION=	23.2.0
DISTNAME=	pyOpenSSL-${MODPY_EGG_VERSION}
PKGNAME=	py-openssl-${MODPY_EGG_VERSION}
CATEGORIES=	security devel

HOMEPAGE=	https://github.com/pyca/pyopenssl

# Apache 2
PERMIT_PACKAGE=	Yes

WANTLIB += ${MODPY_WANTLIB}
WANTLIB += crypto pthread ssl

FLAVORS=	python3
FLAVOR=		python3

RUN_DEPENDS=	security/py-cryptography${MODPY_FLAVOR}
BUILD_DEPENDS=	${RUN_DEPENDS}

MODULES=	lang/python
MODPY_PI=	Yes
MODPY_PYBUILD=	setuptools
# disable test which stops others from running
MODPY_PYTEST_ARGS= -k 'not test_it_works_at_all'

TEST_DEPENDS=	devel/py-flaky${MODPY_FLAVOR} \
		devel/py-pretend${MODPY_FLAVOR}

.include <bsd.port.mk>
