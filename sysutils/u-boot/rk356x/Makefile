VERSION=	2023.10

SOC=		rk356x

BOARDS=\
	odroid-m1-rk3568 \
	quartz64-a-rk3566 \
	quartz64-b-rk3566 \
	radxa-cm3-io-rk3566 \
	soquartz-blade-rk3566 \
	soquartz-cm4-rk3566 \
	soquartz-model-a-rk3566 \
	nanopi-r5c-rk3568 \
	nanopi-r5s-rk3568 \
	radxa-e25-rk3568 \
	rock-3a-rk3568

BUILD_DEPENDS+= devel/arm-none-eabi/gcc,aarch64 \
		devel/py-elftools${MODPY_FLAVOR} \
		shells/bash \
		sysutils/e2fsprogs
CROSS_COMPILE=	aarch64-none-elf-

RK3566_TPL=	rk3566_ddr_1056MHz_v1.18.bin
RK3568_TPL=	rk3568_ddr_1560MHz_v1.18.bin
RK356X_BL31=	rk3568_bl31_v1.43.elf

DISTFILES.rkbin= ${RK3566_TPL} ${RK3568_TPL} ${RK356X_BL31}
SITES.rkbin=	https://github.com/rockchip-linux/rkbin/raw/master/bin/rk35/
EXTRACT_ONLY=	${DISTNAME}${EXTRACT_SUFX}

MAKE_ENV+=	BL31=${FULLDISTDIR}/${RK356X_BL31}

pre-build:
	cc -o ${WRKSRC}/rkbinpatch ${FILESDIR}/rkbinpatch.c 
	cd ${WRKSRC} && \
	    cp ${FULLDISTDIR}/${RK3566_TPL} . && \
	    ./rkbinpatch ${RK3566_TPL}
	cd ${WRKSRC} && \
	    cp ${FULLDISTDIR}/${RK3568_TPL} . && \
	    ./rkbinpatch ${RK3568_TPL}

.include <bsd.port.mk>
