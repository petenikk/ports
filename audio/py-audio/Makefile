COMMENT =	Python bindings for PortAudio

MODPY_EGG_VERSION =	0.2.13
REVISION =	0
DISTNAME =	PyAudio-${MODPY_EGG_VERSION}
PKGNAME =	py-audio-${MODPY_EGG_VERSION}
CATEGORIES =	audio devel

HOMEPAGE =	http://people.csail.mit.edu/hubert/pyaudio/

# MIT
PERMIT_PACKAGE =	Yes

WANTLIB =	portaudio

FLAVOR =	python3
FLAVORS =	python3

MODULES =	lang/python

MODPY_PI =	Yes
MODPY_PYBUILD =	setuptools

MODPY_PYTEST_ARGS =	tests/*

LIB_DEPENDS =	audio/portaudio-svn

.include <bsd.port.mk>
