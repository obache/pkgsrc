# $NetBSD: Makefile,v 1.4 2020/07/01 16:03:59 adam Exp $

DISTNAME=	arviz-0.9.0
PKGNAME=	${PYPKGPREFIX}-${DISTNAME}
CATEGORIES=	math python
MASTER_SITES=	${MASTER_SITE_PYPI:=a/arviz/}

MAINTAINER=	minskim@NetBSD.org
HOMEPAGE=	https://arviz-devs.github.io/arviz/
COMMENT=	Exploratory analysis of Bayesian models
LICENSE=	apache-2.0

DEPENDS+=	${PYPKGPREFIX}-matplotlib>=3.0:../../graphics/py-matplotlib
DEPENDS+=	${PYPKGPREFIX}-netCDF4-[0-9]*:../../math/py-netCDF4
DEPENDS+=	${PYPKGPREFIX}-numpy>=1.12:../../math/py-numpy
DEPENDS+=	${PYPKGPREFIX}-packaging-[0-9]*:../../devel/py-packaging
DEPENDS+=	${PYPKGPREFIX}-pandas>=0.23:../../math/py-pandas
DEPENDS+=	${PYPKGPREFIX}-scipy>=0.19:../../math/py-scipy
DEPENDS+=	${PYPKGPREFIX}-xarray>=0.11:../../math/py-xarray

USE_LANGUAGES=	# none

PYTHON_VERSIONS_INCOMPATIBLE=	27

.include "../../lang/python/egg.mk"
.include "../../mk/bsd.pkg.mk"
