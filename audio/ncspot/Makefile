# $NetBSD: Makefile,v 1.13 2021/01/01 09:52:17 ryoon Exp $

DISTNAME=	ncspot-0.2.6
PKGREVISION=	2
CATEGORIES=	audio
MASTER_SITES=	${MASTER_SITE_GITHUB:=hrkfdn/}
GITHUB_TAG=	v${PKGVERSION_NOREV}

MAINTAINER=	pin@NetBSD.org
HOMEPAGE=	https://github.com/hrkfdn/ncspot/
COMMENT=	Cross-platform ncurses Spotify client written in Rust
LICENSE=	2-clause-bsd

.include "cargo-depends.mk"

USE_LANGUAGES+=			c c++	# rust, but needs a toolchain to link
USE_TOOLS+=			pkg-config
PYTHON_VERSIONS_INCOMPATIBLE=	27
PYTHON_FOR_BUILD_ONLY=		tool

INSTALLATION_DIRS=	bin

MAKE_ENV+=	OPENSSL_DIR=${BUILDLINK_PREFIX.openssl:Q}
RUSTFLAGS+=	-C link-arg=${COMPILER_RPATH_FLAG}${BUILDLINK_PREFIX.openssl}/lib
MAKE_ENV+=	RUSTFLAGS=${RUSTFLAGS:Q}

CARGO_NO_DEFAULT_FEATURES=	YES

.include "options.mk"

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/target/release/ncspot ${DESTDIR}${PREFIX}/bin

.include "../../lang/python/tool.mk"
.include "../../lang/rust/cargo.mk"
.include "../../security/openssl/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
