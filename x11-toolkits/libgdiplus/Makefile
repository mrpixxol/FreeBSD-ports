# Created by: Tom McLaughlin <tmclaugh@sdf.lonestar.org>
# $FreeBSD$

PORTNAME=	libgdiplus
PORTVERSION=	4.2
PORTREVISION=	1
CATEGORIES=	x11-toolkits
MASTER_SITES=	http://download.mono-project.com/sources/${PORTNAME}/

MAINTAINER=	mono@FreeBSD.org
COMMENT=	GDI+ API for System.Windows.Forms in Mono

LICENSE=	MPL
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libtiff.so:graphics/tiff \
		libgif.so:graphics/giflib \
		libpng.so:graphics/png \
		libcairo.so:graphics/cairo \
		libfreetype.so:print/freetype2 \
		libexif.so:graphics/libexif \
		libfontconfig.so:x11-fonts/fontconfig

GNU_CONFIGURE=	yes
USES=		cpe gettext-runtime gmake jpeg libtool:keepla pathfix pkgconfig
USE_GNOME=	glib20
USE_LDCONFIG=	yes
CPPFLAGS+=	-I${LOCALBASE}/include
LDFLAGS+=	-L${LOCALBASE}/lib
INSTALL_TARGET=	install-strip
CPE_VENDOR=	mono-project

OPTIONS_DEFINE=	X11
OPTIONS_DEFAULT=X11

X11_USE=	XORG=x11,xrender
X11_CONFIGURE_OFF=	--without-x11
X11_EXTRA_PATCHES_OFF=	${PATCHDIR}/extrapatch-nox11
X11_USES_OFF=	autoreconf

PLIST_FILES=	lib/libgdiplus.a \
		lib/libgdiplus.la \
		lib/libgdiplus.so \
		lib/libgdiplus.so.0 \
		lib/libgdiplus.so.0.0.0 \
		libdata/pkgconfig/libgdiplus.pc

.include <bsd.port.mk>
