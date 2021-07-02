# JAI-ImageIO

[![](https://github.com/scifio/scifio-jai-imageio/actions/workflows/build-main.yml/badge.svg)](https://github.com/scifio/scifio-jai-imageio/actions/workflows/build-main.yml)

Purpose
-------

A fork of the Java API to handle JPEG and JPEG2000 files. Used by SCIFIO
to read images compressed with JPEG2000 and lossless JPEG. Modified from
the 2008-10-14 source to include support for the YCbCr color space.
Several files in the com.sun.media.jai packages were removed, as they are
not needed by SCIFIO, and created an additional dependency. This project
will be removed once our changes have been added to the official JAI CVS
repository.

Building the Java Advanced Imaging Image I/O Tools Packages
-----------------------------------------------------------

To build the Java Advanced Imaging Image I/O Tools packages, you must
first checkout the [jai-imageio-core](http://jai-imageio-core.dev.java.net/)
CVS repository on java.net. For example, run the cvs checkout command as follows:

* cd cvs-root-dir
* cvs checkout jai-imageio-core

Any operating environment that supports J2SE should work. We have built
jai-imageio-core on the following operating environments:
* Solaris-sparc: Sparc (Ultra60 or better) running Solaris 9
* Solaris-x86: i386/i586 running Solaris-x86 9
* Linux: i386/i586 running SuSE 9 or RedHat 9.0
* Windows: Windows/XP, Windows 2000

The following software must be installed:
* [J2SE 1.4](http://java.sun.com/j2se) or later.
* [Apache Ant 1.6](http://jakarta.apache.org/ant) or later.


Building Java Advanced Imaging Image I/O Tools
----------------------------------------------

Before you start building, your PATH must include these directories:
* ant-root-dir/bin
* jdk-root-dir/bin

and Java Advanced Imaging (JAI) must be be referenced either by JAI being
installed in the J2SDK used for the build; or jai_core.jar being on the
CLASSPATH.


Setting the JAVA_HOME or JAVACMD environment variable will supersede
jdk-root-dir/bin for ant. For further details please refer to
the ant manual.

The default target, jar, creates both optimized and debug jar files.

To build:

* cd cvs-root-dir/jai-imageio-core
* ant

The above steps build the Java code for the jj2000, com.sun.media.imageio,
com.sun.media.imageioimpl, com.sun.media.jai.imageioimpl and
com.sun.media.jai.operator packages.  The build will be placed in
jai-imageio-core/build/platform/opt where platform is determined from the ant
echo command:

* ant echo

Jar files are placed in jai-imageio-core/build/platform/opt/lib/ext.  Binaries
for native libraries are part of the project and are copied to the
jai-imageio-core/build/platform/opt/jrenativesubdir directory as part of the
build, where jrenativesubdiris determined from the ant echo command as above.

To see other targets that are available, type "ant -projecthelp". Note that ant
must be run from the top-level directory.


Running Java Advanced Imaging Image I/O Tools
---------------------------------------------

To run Java Advanced Imaging Image I/O Tools, please checkout the
[jai-imageio-demos](https://jai-imageio-demos.dev.java.net/) project and then
refer to [README-build.html](../jai-imageio-demos/README-build.html) in
jai-imageio-demos for details on building and running Java Advanced Imaging
Image I/O Tools demo programs.
