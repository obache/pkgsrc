# $NetBSD: Makefile,v 1.20 2020/08/24 15:31:12 pho Exp $

DISTNAME=	cgrep-6.6.30
#PKGNAME=	${DISTNAME} # This package should probably be renamed to textproc/cgrep
CATEGORIES=	textproc

MAINTAINER=	szptvlfn@NetBSD.org
COMMENT=	Context-aware grep for source codes
LICENSE=	gnu-gpl-v2

# Do not install the LICENCE file because ../../mk/haskell.mk can not
# correctly substitute the path to doc files when the package installs
# no libraries.
post-install:
	${RM} -rf ${DESTDIR}${PREFIX}/share/doc

.include "../../mk/haskell.mk"
.include "../../converters/hs-aeson/buildlink3.mk"
.include "../../devel/hs-ansi-terminal/buildlink3.mk"
.include "../../devel/hs-async/buildlink3.mk"
.include "../../devel/hs-cmdargs/buildlink3.mk"
.include "../../devel/hs-dlist/buildlink3.mk"
.include "../../devel/hs-either/buildlink3.mk"
.include "../../devel/hs-exceptions/buildlink3.mk"
.include "../../misc/hs-extra/buildlink3.mk"
.include "../../textproc/hs-regex-base/buildlink3.mk"
.include "../../textproc/hs-regex-pcre/buildlink3.mk"
.include "../../textproc/hs-regex-posix/buildlink3.mk"
.include "../../devel/hs-safe/buildlink3.mk"
.include "../../devel/hs-split/buildlink3.mk"
.include "../../textproc/hs-stringsearch/buildlink3.mk"
.include "../../textproc/hs-unicode-show/buildlink3.mk"
.include "../../devel/hs-unix-compat/buildlink3.mk"
.include "../../devel/hs-unordered-containers/buildlink3.mk"
.include "../../devel/hs-utf8-string/buildlink3.mk"
.include "../../textproc/hs-yaml/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
