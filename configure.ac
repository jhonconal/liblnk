AC_PREREQ( 2.59 )

AC_INIT(
 [liblnk],
 [20170305],
 [joachim.metz@gmail.com])

AC_CONFIG_SRCDIR(
 [include/liblnk.h.in])

AM_INIT_AUTOMAKE([gnu 1.6 tar-ustar])

AC_CONFIG_MACRO_DIR([m4])

dnl Check for host type
AC_CANONICAL_HOST

dnl Check for large file support
AC_SYS_LARGEFILE

dnl Check for libtool DLL support
AC_LIBTOOL_WIN32_DLL

dnl Checks for programs
AC_PROG_CC
AC_PROG_GCC_TRADITIONAL
AC_PROG_MAKE_SET
AC_PROG_INSTALL

dnl Check for libtool
AC_PROG_LIBTOOL
AC_SUBST(LIBTOOL_DEPS)

dnl Check for pkg-config
AC_PATH_PROG(PKGCONFIG,[pkg-config])

dnl Support of internationalization (i18n)
AM_GNU_GETTEXT([external])
AM_GNU_GETTEXT_VERSION([0.18.1])

dnl Check for compiler language support
AC_C_CONST
AC_C_VOLATILE

dnl Check if WINAPI support should be enabled
AX_COMMON_CHECK_ENABLE_WINAPI

dnl Check if wide character type should be enabled
AX_COMMON_CHECK_ENABLE_WIDE_CHARACTER_TYPE

dnl Check for type definitions
AX_TYPES_CHECK_LOCAL

dnl Checks for libraries and library functions
AX_COMMON_CHECK_LOCAL

dnl Check for enabling libcerror for cross-platform C error functions
AX_LIBCERROR_CHECK_ENABLE

dnl Check for enabling libcthreads for cross-platform C threads functions
AX_LIBCTHREADS_CHECK_ENABLE

dnl Check for enabling libcdata for cross-platform C generic data functions
AX_LIBCDATA_CHECK_ENABLE

dnl Check for enabling libclocale for cross-platform C locale functions
AX_LIBCLOCALE_CHECK_ENABLE

dnl Check for enabling libcnotify for cross-platform C notification functions
AX_LIBCNOTIFY_CHECK_ENABLE

dnl Check for enabling libcsplit for cross-platform C split string functions
AX_LIBCSPLIT_CHECK_ENABLE

dnl Check for enabling libuna for Unicode string support
AX_LIBUNA_CHECK_ENABLE

dnl Check for enabling libcfile for cross-platform C file functions
AX_LIBCFILE_CHECK_ENABLE

dnl Check for enabling libcpath for cross-platform C path functions
AX_LIBCPATH_CHECK_ENABLE

dnl Check for enabling libbfio for basic file IO support
AX_LIBBFIO_CHECK_ENABLE

dnl Check for enabling libfdatetime for date and time formats support
AX_LIBFDATETIME_CHECK_ENABLE

dnl Check for enabling libfguid for GUID/UUID format support
AX_LIBFGUID_CHECK_ENABLE

dnl Check for enabling libfole for file OLE types support
AX_LIBFOLE_CHECK_ENABLE

dnl Check for enabling libfwps for Windows Property Store support
AX_LIBFWPS_CHECK_ENABLE

dnl Check for enabling libfwsi for Windows Shell identifier support
AX_LIBFWSI_CHECK_ENABLE

dnl Check for library function support
AX_LIBLNK_CHECK_LOCAL

dnl Check for lnktools function support
AX_LNKTOOLS_CHECK_LOCAL

dnl Check if liblnk python bindings (pylnk) should be build
AX_PYTHON_CHECK_PYPREFIX
AX_PYTHON_CHECK_ENABLE
AX_PYTHON2_CHECK_ENABLE
AX_PYTHON3_CHECK_ENABLE

AM_CONDITIONAL(
 HAVE_PYTHON_TESTS,
 [test "x${ac_cv_enable_python}" != xno || test "x${ac_cv_enable_python2}" != xno || test "x${ac_cv_enable_python3}" != xno])

dnl Headers included in various places
AC_CHECK_HEADERS([stdarg.h varargs.h])

AS_IF(
 [test "x$ac_cv_header_stdarg_h" != xyes && test "x$ac_cv_header_varargs_h" != xyes],
 [AC_MSG_FAILURE(
  [Missing headers: stdarg.h and varargs.h],
  [1])
 ])

dnl Check for test function support
AX_TESTS_CHECK_LOCAL

dnl Set additional compiler flags
CFLAGS="$CFLAGS -Wall";

dnl Check if requires and build requires should be set in spec file
AS_IF(
 [test "x$ac_cv_libcerror" = xyes || test "x$ac_cv_libcthreads" = xyes || test "x$ac_cv_libcdata" = xyes ||  test "x$ac_cv_libclocale" = xyes || test "x$ac_cv_libcnotify" = xyes || test "x$ac_cv_libcsplit" = xyes || test "x$ac_cv_libuna" = xyes || test "x$ac_cv_libcfile" = xyes || test "x$ac_cv_libcpath" = xyes || test "x$ac_cv_libbfio" = xyes || test "x$ac_cv_libfdatetime" = xyes || test "x$ac_cv_libfguid" = xyes || test "x$ac_cv_libfole" = xyes || test "x$ac_cv_libfwps" = xyes || test "x$ac_cv_libfwsi" = xyes],
 [AC_SUBST(
  [liblnk_spec_requires],
  [Requires:])
 AC_SUBST(
  [liblnk_spec_build_requires],
  [BuildRequires:])
 ])

dnl Set the date for the dpkg files
AC_SUBST(
 [DPKG_DATE],
 [`date -R 2> /dev/null`])

dnl Set the date for the spec file
AC_SUBST(
 [SPEC_DATE],
 [`date +"%a %b %e %Y" 2> /dev/null`])

dnl Set the current working directory for PackageMaker files
AC_SUBST(
 [PWD],
 [`pwd`])

dnl Have configure make the Makefiles
AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([include/Makefile])
AC_CONFIG_FILES([common/Makefile])
AC_CONFIG_FILES([libcerror/Makefile])
AC_CONFIG_FILES([libcthreads/Makefile])
AC_CONFIG_FILES([libcdata/Makefile])
AC_CONFIG_FILES([libclocale/Makefile])
AC_CONFIG_FILES([libcnotify/Makefile])
AC_CONFIG_FILES([libcsplit/Makefile])
AC_CONFIG_FILES([libuna/Makefile])
AC_CONFIG_FILES([libcfile/Makefile])
AC_CONFIG_FILES([libcpath/Makefile])
AC_CONFIG_FILES([libbfio/Makefile])
AC_CONFIG_FILES([libfdatetime/Makefile])
AC_CONFIG_FILES([libfguid/Makefile])
AC_CONFIG_FILES([libfole/Makefile])
AC_CONFIG_FILES([libfwps/Makefile])
AC_CONFIG_FILES([libfwsi/Makefile])
AC_CONFIG_FILES([liblnk/Makefile])
AC_CONFIG_FILES([lnktools/Makefile])
AC_CONFIG_FILES([pylnk/Makefile])
AC_CONFIG_FILES([pylnk-python2/Makefile])
AC_CONFIG_FILES([pylnk-python3/Makefile])
AC_CONFIG_FILES([po/Makefile.in])
AC_CONFIG_FILES([po/Makevars])
AC_CONFIG_FILES([manuals/Makefile])
AC_CONFIG_FILES([tests/Makefile])
AC_CONFIG_FILES([msvscpp/Makefile])
dnl Have configure make the include files
AC_CONFIG_FILES([include/liblnk.h])
AC_CONFIG_FILES([include/liblnk/definitions.h])
AC_CONFIG_FILES([include/liblnk/features.h])
AC_CONFIG_FILES([include/liblnk/types.h])
AC_CONFIG_FILES([liblnk/liblnk_definitions.h])
dnl Have configure make distribution specific files
AC_CONFIG_FILES([common/types.h])
AC_CONFIG_FILES([dpkg/changelog])
AC_CONFIG_FILES([dpkg/copyright])
AC_CONFIG_FILES([liblnk/liblnk.rc])
AC_CONFIG_FILES([liblnk.pc])
AC_CONFIG_FILES([liblnk.spec])
dnl Have configure write its configuration
AC_CONFIG_HEADERS([common/config.h])

AC_OUTPUT

dnl Print a summary
AC_MSG_NOTICE([
Building:
   libcerror support:                        $ac_cv_libcerror
   libcthreads support:                      $ac_cv_libcthreads
   libcdata support:                         $ac_cv_libcdata
   libclocale support:                       $ac_cv_libclocale
   libcnotify support:                       $ac_cv_libcnotify
   libcsplit support:                        $ac_cv_libcsplit
   libuna support:                           $ac_cv_libuna
   libcfile support:                         $ac_cv_libcfile
   libcpath support:                         $ac_cv_libcpath
   libbfio support:                          $ac_cv_libbfio
   libfdatetime support:                     $ac_cv_libfdatetime
   libfguid support:                         $ac_cv_libfguid
   libfole support:                          $ac_cv_libfole
   libfwps support:                          $ac_cv_libfwps
   libfwsi support:                          $ac_cv_libfwsi

Features:
   Multi-threading support:                  $ac_cv_libcthreads_multi_threading
   Wide character type support:              $ac_cv_enable_wide_character_type
   lnktools are build as static executables: $ac_cv_enable_static_executables
   Python (pylnk) support:                   $ac_cv_enable_python
   Python version 2 (pylnk) support:         $ac_cv_enable_python2
   Python version 3 (pylnk) support:         $ac_cv_enable_python3
   Verbose output:                           $ac_cv_enable_verbose_output
   Debug output:                             $ac_cv_enable_debug_output
]);


