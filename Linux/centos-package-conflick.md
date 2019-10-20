```
warning: lib64stdc++6-4.6.1-2-mdv2011.0.x86_64.rpm: Header V3 DSA/SHA1 Signature, key ID 70771ff3: NOKEY
Preparing...                ########################################### [100%]
    file /usr/lib64/libstdc++.so.6 from install of lib64stdc++6-4.6.1-2.x86_64 conflicts with file from package libstdc++-4.4.7-11.el6.x86_64
    file /usr/lib64/libstdc++.so.6 from install of lib64stdc++6-4.6.1-2.i686 conflicts with file from package libstdc++-4.4.7-11.el6.i686
```

解决方法: 卸载冲突的包

```shell
yum -y remove libstdc++-4.4.7-11.el6.i686
yum -y remove libstdc++-4.4.7-11.el6.x86_64
```

- [https://www.howtoing.com/linux-yum-package-management-with-yum-utils]
- [https://www.howtoing.com/install-epel-and-remi-repository-on-centos-and-redhat]
- [http://www.voidcn.com/article/p-zmujenao-vc.html]
