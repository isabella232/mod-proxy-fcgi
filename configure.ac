AC_INIT([mod_proxy_fcgi], [2.4.10], [yehudasa@redhat.com])
AC_DEFINE([PACKAGE_URL],["https://github.com/ceph/mod-proxy-fcgi"],[project url])

AC_PROG_CC

AC_PATH_PROG(APXS, 'apxs')

if test x"$APXS" = x"" ; then
  AC_CHECK_FILE([/etc/redhat-release],
    [AC_MSG_FAILURE([apxs is missing, run "sudo yum install httpd-devel"])],
    [AC_MSG_FAILURE([apxs is missing, run "sudo apt-get install apache2-dev"])])
fi

APXS_PREFIX=`$APXS -q prefix`
APXS_INSTALLBUILDDIR=`$APXS -q installbuilddir`
AC_SUBST([APXS_PREFIX])
AC_SUBST([APXS_INSTALLBUILDDIR])

AC_OUTPUT(Makefile)
