# $NetBSD: Makefile,v 1.49 2020/11/05 09:07:18 ryoon Exp $

DISTNAME=	libxklavier-5.4
PKGREVISION=	6
CATEGORIES=	x11
MASTER_SITES=	http://pkgs.fedoraproject.org/repo/pkgs/libxklavier/libxklavier-5.4.tar.bz2/13af74dcb6011ecedf1e3ed122bd31fa/
EXTRACT_SUFX=	.tar.bz2

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://freedesktop.org/Software/LibXklavier
COMMENT=	High-level API for the X Keyboard Extension (XKB)
LICENSE=	gnu-lgpl-v2

USE_TOOLS+=		gmake pkg-config
GNU_CONFIGURE=		YES
USE_LIBTOOL=		YES

PKGCONFIG_OVERRIDE=	libxklavier.pc.in

CONFIGURE_ARGS+=	--enable-xkb-support
CONFIGURE_ARGS+=	--with-xmodmap-base=${PREFIX}/share/xmodmap
CONFIGURE_ARGS+=	--disable-introspection

.include "../../mk/bsd.prefs.mk"
.if exists(${X11BASE}/share/X11/xkb/rules/xorg.xml)
CONFIGURE_ARGS+=	--with-xkb-base=${X11BASE}/share/X11/xkb
.else
CONFIGURE_ARGS+=	--with-xkb-base=${X11BASE}/lib/X11/xkb
.endif

BUILDLINK_API_DEPENDS.glib2+=	glib2>=2.6.0

.include "../../devel/glib2/buildlink3.mk"
#.include "../../devel/gobject-introspection/buildlink3.mk"
.include "../../textproc/iso-codes/buildlink3.mk"
.include "../../textproc/libxml2/buildlink3.mk"
.include "../../x11/libX11/buildlink3.mk"
BUILDLINK_API_DEPENDS.libXi+=	libXi>=1.1.3
.include "../../x11/libXi/buildlink3.mk"
.include "../../x11/libxkbfile/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
