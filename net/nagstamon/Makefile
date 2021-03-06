# $NetBSD: Makefile,v 1.65 2020/12/04 20:45:35 nia Exp $

VERSION=	1.0.1
DISTNAME=	Nagstamon-${VERSION}
PKGNAME=	${DISTNAME:S/N/n/}
PKGREVISION=	19
CATEGORIES=	net python
MASTER_SITES=	https://nagstamon.ifw-dresden.de/files-nagstamon/stable/

MAINTAINER=	imil@gcu.info
HOMEPAGE=	https://nagstamon.ifw-dresden.de/
COMMENT=	Nagios status monitor which takes place in systray or on desktop
LICENSE=	gnu-gpl-v2

DEPENDS+=	librsvg-[0-9]*:../../graphics/librsvg
DEPENDS+=	${PYPKGPREFIX}-beautifulsoup-[0-9]*:../../www/py-beautifulsoup
DEPENDS+=	${PYPKGPREFIX}-gtk2-[0-9]*:../../x11/py-gtk2
DEPENDS+=	sox>=14.0.1:../../audio/sox

USE_LANGUAGES=		# none

WRKSRC=			${WRKDIR}/Nagstamon

INSTALLATION_DIRS+=	${PKGMANDIR}/man1
REPLACE_PYTHON=		${WRKSRC}/*.py
REPLACE_PYTHON+=	${WRKSRC}/Nagstamon/Server/Multisite.py

PYTHON_VERSIONS_ACCEPTED=	27 # py-gtk2

SUBST_CLASSES+=		mandir
SUBST_STAGE.mandir=	pre-configure
SUBST_VARS.mandir=	PKGMANDIR
SUBST_FILES.mandir=	setup.py

# Upstream renamed script from nagstamon to nagstamon.py
# Preserve compatibility with previous version of the package
post-install:
	${LN} -s ${DESTDIR}${PREFIX}/bin/nagstamon.py \
		${DESTDIR}${PREFIX}/bin/nagstamon

EGG_NAME=	${DISTNAME:tl}

.include "../../lang/python/application.mk"
.include "../../lang/python/distutils.mk"
.include "../../mk/bsd.pkg.mk"
