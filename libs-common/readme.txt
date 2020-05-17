New notes
=========

I updated some of the libs and dlls with those from the vcpkgs project (https://github.com/microsoft/vcpkg). This includes both x86 and x64. Specifically I got zlib, and cairo (and dependencies).

Old notes
=========

i386
----

xdr.lib and xdr-0.dll are the import library and shared build of bsd-xdr-1.0.0 available from http://code.google.com/p/bsd-xdr/. These were built from source by starting the MSVC2008 shell, starting bash (provided by Cygwin), and running the command "make -f Makefile.msvc80".

The include files in %ROOT%/windows-vc2008/include are also from this code base.

Cairo and its dependencies (freetype, expat, fontconfig, libpng) were downloaded from 
http://www.gtk.org/download-windows.html. The Cairo include files and cairo.lib were taken
from Cairo Dev from that same webpage.

x64
---
To create the zlib1 dll and lib, I did the following:

(1) Got zlib124.zip from http://www.winimage.com/zLibDll/index.html
(2) Opened zlib.dsw into MSVC++ 2008
(3) In Configuration manager for zlib, make a x64 target
(4) Make the DLL Release =>  zlib-1.2.4\projects\visualc6\Win32_DLL_Release\zlib1.dll and zlib1.lib

To create libinchi

(1) Got INCHI-1-API.zip (InChI v 1.0.4) from http://www.inchi-trust.org/index.php?q=node/14
(2) Open INCHI-1-API\INCHI_API\vc9\inchi_dll\inchi_dll.sln in VC9
(3) Change afxres.h to windows.h in INCHI_DLL.rc
(4) In configuration manager, make an x64 target
(5) Creates x64\Release\libinchi.lib and .dll

The libxml files were downloaded as binaries from the PHP project:

(1) Got libxml2-2.7.3-vc9-x64.zip from http://pecl2.php.net/downloads/php-windows-builds/php-libs/VC9/x64/
(2) Extracted libxml2.lib and libxml2.dll

libiconv.dll (required for XML) was also downloaded as a binary from the PHP project:

(1) Got libiconv-1.12-vc9-x64.zip from http://pecl2.php.net/downloads/php-windows-builds/php-libs/VC9/x64/
(2) Extracted libiconv.dll

xdr:

(1) Built from https://github.com/baoilleach/bsd-xdr

libcairo, libexpat, fonconfig, freetype, pixman and png were compiled with MinGW64. cairo.lib is from https://github.com/cairoD/cairoD/tree/master/lib/64, though presumably there is some way to generate it from the cairo build.
