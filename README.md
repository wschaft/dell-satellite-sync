# dell-satellite-sync

If you're using Red Hat Satellite (or Spacewalk) for RHEL (or CentOS) package management, you may want to add the Dell repositories when you've 1 or more Dell servers running.

Dell provides a tool (dell-satellite-sync) to import the Dell OpenManage yum repositories into an RHN Satellite / Spacewalk server and subscribe registered servers to the corresponding OpenManage channels.

However, there's no support for CentOS. There is a patch for CentOS 6 available at http://linux.dell.com/dell-satellite-sync/centos/, but none for CentOS 7.

This patch adds support for the CentOS 6 and 7 x86_64 parent channels in
dell-satellite-sync.py, and will use the RHEL 6 and 7 x86_64 repositories
in http://linux.dell.com/repo/hardware/latest.

To apply, place the corresponding patch in the same directory as dell-satellite-sync.py (/usr/share/dell-satellite-sync) and run:

$ patch -p1 < dell-satellite-sync-centos.patch

Notes:

* assumes name of CentOS 6 x86_64 channel is 'centos-x86_64-server-6'
* assumes name of CentOS 7 x86_64 channel is 'centos-x86_64-server-7'
