# ZFontIcon - Icon fonts support for Qt applications
ZFontIcon is released under the MIT License

## Description
ZFontIcon provide a simple way to use any glyph/icon fonts as QIcon in your Qt applications.

Some helpers are included to use the following icon fonts without effort:
- Google Material Design Icons 2.2.0
- Font Awesome 5 Free
- Font Awesome 5 Pro (you need to have a license)
- Font Awesome 5 Brands
- Font Awesome 4.7.0

You can use any other icon fonts using Unicode character codes.
For convenience, you can also create your own font helper: Simply create an enumeration listing all the unicode characters of the font icons. Take a look at the code, it's very easy.


## Installation
The easiest way to include ZFontIcon in your project is to copy the ZFontIcon folder to your project tree and add the following include() to your Qt project (.pro) file:

    include(ZFontIcon/ZFontIcon.pri)

Now, you are ready !


## Usage
First of all, you need load the fonts (typically in the main.cpp):

    ZFontIcon::addFont(":/fa_5.13.0/" + FA5_OTF_FILE_FREE_SOLID);
    ZFontIcon::addFont(":/fa_5.13.0/" + FA5_OTF_FILE_FREE_REGULAR);
    ZFontIcon::addFont(":/fa_5.13.0/" + FA5_OTF_FILE_BRANDS);

Then you can get icon using the helpers:

    #include "ZFontIcon/ZFont_fa_5.13.h"
    ZFontIcon::icon(Fa5::FAMILY,       Fa5::fa_flag,         Fa5::SOLID,      QColor(0, 0, 0));
    ZFontIcon::icon(Fa5::FAMILY,       Fa5::fa_flag,         Fa5::REGULAR,    QColor(0, 0, 0));
    ZFontIcon::icon(Fa5pro::FAMILY,    Fa5pro::fa_flag,      Fa5pro::LIGHT,   QColor(0, 0, 0));
    ZFontIcon::icon(Fa5brands::FAMILY, Fa5brands::fa_github,                  QColor(0, 0, 0));

Or get icon from unicode (without helpers):

    ZFontIcon::icon(QLatin1String("Font Awesome 5 Free"),   0xf024, QLatin1String("Solid"),   QColor(0, 0, 0));
    ZFontIcon::icon(QLatin1String("Font Awesome 5 Free"),   0xf024, QLatin1String("Regular"), QColor(0, 0, 0));
    ZFontIcon::icon(QLatin1String("Font Awesome 5 Pro"),    0xf024, QLatin1String("Light"),   QColor(0, 0, 0));
    ZFontIcon::icon(QLatin1String("Font Awesome 5 Brands"), 0xf09b,                           QColor(0, 0, 0));


## Exemple
The following repository contains a commented example based on Font Awesome 5.
Open ZFontIcon.pro in QtCreator and run it or read sources for more information.


## Credits
ZFontIcon is inspired/based on:
- QFontIcon by Sacha Schutz - sacha@labsquare.org | https://github.com/dridk