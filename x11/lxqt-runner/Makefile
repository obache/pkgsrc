# $NetBSD: Makefile,v 1.9 2020/12/07 12:49:19 pin Exp $

DISTNAME=	lxqt-runner-0.16.0
CATEGORIES=	x11
MASTER_SITES=	${MASTER_SITE_GITHUB:=lxqt/}
GITHUB_RELEASE=	${PKGVERSION_NOREV}
EXTRACT_SUFX=	.tar.xz

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://github.com/lxqt/lxqt-runner/
COMMENT=	Launch applications quickly by typing commands
LICENSE=	gnu-lgpl-v2.1

USE_CMAKE=	yes
USE_TOOLS+=	pkg-config
USE_LANGUAGES=	c c++

CONFIGURE_DIRS=	build
CMAKE_ARG_PATH=	..

AUTOSTART_CONF=		share/examples/autostart
PKG_SYSCONFSUBDIR=	xdg
MAKE_DIRS=		${PKG_SYSCONFDIR}/autostart

CONF_FILES+=	${AUTOSTART_CONF}/lxqt-runner.desktop \
		${PKG_SYSCONFDIR}/autostart/lxqt-runner.desktop

pre-configure:
	${MKDIR} -p ${WRKSRC}/build

TOOL_DEPENDS+=	lxqt-build-tools>=0.8:../../devel/lxqt-build-tools
TOOL_DEPENDS+=	qt5-qttools-[0-9]*:../../x11/qt5-qttools

.include "../../x11/lxqt-globalkeys/buildlink3.mk"
.include "../../math/muparser/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
