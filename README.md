### Tableau server Linux installation guide
https://help.tableau.com/current/guides/everybody-install-linux/en-us/everybody_admin_intro.htm

### Start an Oracle Linux 7 instance
And ssh to the instance

### Configure firewall
```
sudo firewall-cmd --permanent --add-port=8850/tcp
sudo firewall-cmd --permanent --add-port=80/tcp
sudo firewall-cmd --reload
```

### Download tableau server package for RHEL/CentOS/Oracle Linux
https://www.tableau.com/support/releases/server/2020.1.1

```
wget https://downloads.tableau.com/esdalt/2020.1.1/tableau-server-2020-1-1.x86_64.rpm
```
### Install RPM
```
[opc@frdeng-tabsvr ~]$ sudo yum install ./tableau-server-2020-1-1.x86_64.rpm
Loaded plugins: langpacks, ulninfo
Examining ./tableau-server-2020-1-1.x86_64.rpm: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
Marking ./tableau-server-2020-1-1.x86_64.rpm to be installed
Resolving Dependencies
--> Running transaction check
---> Package tableau-server-20201.20.0305.1738.x86_64 0:20201-20.0305.1738 will be installed
--> Processing Dependency: fontconfig for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: fuse for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: chrpath for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: freeglut for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: fuse-libs for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: libXcomposite for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: libXcursor for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: libXi for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: libXrandr for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: libXrender for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: libxslt for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: libXtst for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: mesa-libEGL for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Processing Dependency: redhat-lsb-core for package: tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64
--> Running transaction check
---> Package chrpath.x86_64 0:0.16-0.el7 will be installed
---> Package fontconfig.x86_64 0:2.13.0-4.3.el7 will be installed
--> Processing Dependency: dejavu-sans-fonts for package: fontconfig-2.13.0-4.3.el7.x86_64
---> Package freeglut.x86_64 0:3.0.0-8.el7 will be installed
--> Processing Dependency: libXxf86vm.so.1()(64bit) for package: freeglut-3.0.0-8.el7.x86_64
--> Processing Dependency: libXext.so.6()(64bit) for package: freeglut-3.0.0-8.el7.x86_64
--> Processing Dependency: libX11.so.6()(64bit) for package: freeglut-3.0.0-8.el7.x86_64
--> Processing Dependency: libICE.so.6()(64bit) for package: freeglut-3.0.0-8.el7.x86_64
--> Processing Dependency: libGL.so.1()(64bit) for package: freeglut-3.0.0-8.el7.x86_64
---> Package fuse.x86_64 0:2.9.4-1.0.4.el7 will be installed
---> Package fuse-libs.x86_64 0:2.9.4-1.0.4.el7 will be installed
---> Package libXcomposite.x86_64 0:0.4.4-4.1.el7 will be installed
---> Package libXcursor.x86_64 0:1.1.15-1.el7 will be installed
--> Processing Dependency: libXfixes.so.3()(64bit) for package: libXcursor-1.1.15-1.el7.x86_64
---> Package libXi.x86_64 0:1.7.9-1.el7 will be installed
---> Package libXrandr.x86_64 0:1.5.1-2.el7 will be installed
---> Package libXrender.x86_64 0:0.9.10-1.el7 will be installed
---> Package libXtst.x86_64 0:1.2.3-1.el7 will be installed
---> Package libxslt.x86_64 0:1.1.28-5.0.1.el7 will be installed
---> Package mesa-libEGL.x86_64 0:18.3.4-6.el7_7 will be installed
--> Processing Dependency: mesa-libgbm = 18.3.4-6.el7_7 for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libglvnd-egl(x86-64) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libxshmfence.so.1()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libxcb.so.1()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libxcb-xfixes.so.0()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libxcb-sync.so.1()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libxcb-present.so.0()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libxcb-dri3.so.0()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libxcb-dri2.so.0()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libwayland-server.so.0()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libwayland-client.so.0()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libglapi.so.0()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libgbm.so.1()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
--> Processing Dependency: libdrm.so.2()(64bit) for package: mesa-libEGL-18.3.4-6.el7_7.x86_64
---> Package redhat-lsb-core.x86_64 0:4.1-27.0.1.el7 will be installed
--> Processing Dependency: redhat-lsb-submod-security(x86-64) = 4.1-27.0.1.el7 for package: redhat-lsb-core-4.1-27.0.1.el7.x86_64
--> Processing Dependency: spax for package: redhat-lsb-core-4.1-27.0.1.el7.x86_64
--> Processing Dependency: /usr/sbin/fuser for package: redhat-lsb-core-4.1-27.0.1.el7.x86_64
--> Processing Dependency: /usr/bin/patch for package: redhat-lsb-core-4.1-27.0.1.el7.x86_64
--> Processing Dependency: /usr/bin/m4 for package: redhat-lsb-core-4.1-27.0.1.el7.x86_64
--> Processing Dependency: /usr/bin/lpr for package: redhat-lsb-core-4.1-27.0.1.el7.x86_64
--> Processing Dependency: /usr/bin/lp for package: redhat-lsb-core-4.1-27.0.1.el7.x86_64
--> Processing Dependency: /usr/bin/killall for package: redhat-lsb-core-4.1-27.0.1.el7.x86_64
--> Running transaction check
---> Package cups-client.x86_64 1:1.6.3-40.el7 will be installed
--> Processing Dependency: cups-libs(x86-64) = 1:1.6.3-40.el7 for package: 1:cups-client-1.6.3-40.el7.x86_64
--> Processing Dependency: libcups.so.2()(64bit) for package: 1:cups-client-1.6.3-40.el7.x86_64
--> Processing Dependency: libavahi-common.so.3()(64bit) for package: 1:cups-client-1.6.3-40.el7.x86_64
--> Processing Dependency: libavahi-client.so.3()(64bit) for package: 1:cups-client-1.6.3-40.el7.x86_64
---> Package dejavu-sans-fonts.noarch 0:2.33-6.el7 will be installed
--> Processing Dependency: dejavu-fonts-common = 2.33-6.el7 for package: dejavu-sans-fonts-2.33-6.el7.noarch
---> Package libICE.x86_64 0:1.0.9-9.el7 will be installed
---> Package libX11.x86_64 0:1.6.7-2.el7 will be installed
--> Processing Dependency: libX11-common >= 1.6.7-2.el7 for package: libX11-1.6.7-2.el7.x86_64
---> Package libXext.x86_64 0:1.3.3-3.el7 will be installed
---> Package libXfixes.x86_64 0:5.0.3-1.el7 will be installed
---> Package libXxf86vm.x86_64 0:1.1.4-1.el7 will be installed
---> Package libdrm.x86_64 0:2.4.97-2.el7 will be installed
--> Processing Dependency: libpciaccess.so.0()(64bit) for package: libdrm-2.4.97-2.el7.x86_64
---> Package libglvnd-egl.x86_64 1:1.0.1-0.8.git5baa1e5.el7 will be installed
--> Processing Dependency: libglvnd(x86-64) = 1:1.0.1-0.8.git5baa1e5.el7 for package: 1:libglvnd-egl-1.0.1-0.8.git5baa1e5.el7.x86_64
--> Processing Dependency: libGLdispatch.so.0()(64bit) for package: 1:libglvnd-egl-1.0.1-0.8.git5baa1e5.el7.x86_64
---> Package libglvnd-glx.x86_64 1:1.0.1-0.8.git5baa1e5.el7 will be installed
--> Processing Dependency: mesa-libGL(x86-64) >= 13.0.4-1 for package: 1:libglvnd-glx-1.0.1-0.8.git5baa1e5.el7.x86_64
---> Package libwayland-client.x86_64 0:1.15.0-1.el7 will be installed
---> Package libwayland-server.x86_64 0:1.15.0-1.el7 will be installed
---> Package libxcb.x86_64 0:1.13-1.el7 will be installed
--> Processing Dependency: libXau.so.6()(64bit) for package: libxcb-1.13-1.el7.x86_64
---> Package libxshmfence.x86_64 0:1.2-1.el7 will be installed
---> Package m4.x86_64 0:1.4.16-10.el7 will be installed
---> Package mesa-libgbm.x86_64 0:18.3.4-6.el7_7 will be installed
---> Package mesa-libglapi.x86_64 0:18.3.4-6.el7_7 will be installed
---> Package patch.x86_64 0:2.7.1-12.el7_7 will be installed
---> Package psmisc.x86_64 0:22.20-16.el7 will be installed
---> Package redhat-lsb-submod-security.x86_64 0:4.1-27.0.1.el7 will be installed
---> Package spax.x86_64 0:1.5.2-13.el7 will be installed
--> Running transaction check
---> Package avahi-libs.x86_64 0:0.6.31-19.el7 will be installed
---> Package cups-libs.x86_64 1:1.6.3-40.el7 will be installed
---> Package dejavu-fonts-common.noarch 0:2.33-6.el7 will be installed
---> Package libX11-common.noarch 0:1.6.7-2.el7 will be installed
---> Package libXau.x86_64 0:1.0.8-2.1.el7 will be installed
---> Package libglvnd.x86_64 1:1.0.1-0.8.git5baa1e5.el7 will be installed
---> Package libpciaccess.x86_64 0:0.14-1.el7 will be installed
---> Package mesa-libGL.x86_64 0:18.3.4-6.el7_7 will be installed
--> Processing Dependency: libXdamage.so.1()(64bit) for package: mesa-libGL-18.3.4-6.el7_7.x86_64
--> Running transaction check
---> Package libXdamage.x86_64 0:1.1.4-4.1.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===============================================================================================================================================
 Package                                    Arch            Version                             Repository                                Size
===============================================================================================================================================
Installing:
 tableau-server-20201.20.0305.1738          x86_64          20201-20.0305.1738                  /tableau-server-2020-1-1.x86_64          3.2 G
Installing for dependencies:
 avahi-libs                                 x86_64          0.6.31-19.el7                       ol7_latest                                61 k
 chrpath                                    x86_64          0.16-0.el7                          ol7_latest                                26 k
 cups-client                                x86_64          1:1.6.3-40.el7                      ol7_latest                               151 k
 cups-libs                                  x86_64          1:1.6.3-40.el7                      ol7_latest                               357 k
 dejavu-fonts-common                        noarch          2.33-6.el7                          ol7_latest                                64 k
 dejavu-sans-fonts                          noarch          2.33-6.el7                          ol7_latest                               1.4 M
 fontconfig                                 x86_64          2.13.0-4.3.el7                      ol7_latest                               254 k
 freeglut                                   x86_64          3.0.0-8.el7                         ol7_latest                               185 k
 fuse                                       x86_64          2.9.4-1.0.4.el7                     ol7_latest                                86 k
 fuse-libs                                  x86_64          2.9.4-1.0.4.el7                     ol7_latest                                95 k
 libICE                                     x86_64          1.0.9-9.el7                         ol7_latest                                66 k
 libX11                                     x86_64          1.6.7-2.el7                         ol7_latest                               606 k
 libX11-common                              noarch          1.6.7-2.el7                         ol7_latest                               164 k
 libXau                                     x86_64          1.0.8-2.1.el7                       ol7_latest                                28 k
 libXcomposite                              x86_64          0.4.4-4.1.el7                       ol7_latest                                22 k
 libXcursor                                 x86_64          1.1.15-1.el7                        ol7_latest                                30 k
 libXdamage                                 x86_64          1.1.4-4.1.el7                       ol7_latest                                20 k
 libXext                                    x86_64          1.3.3-3.el7                         ol7_latest                                38 k
 libXfixes                                  x86_64          5.0.3-1.el7                         ol7_latest                                18 k
 libXi                                      x86_64          1.7.9-1.el7                         ol7_latest                                40 k
 libXrandr                                  x86_64          1.5.1-2.el7                         ol7_latest                                27 k
 libXrender                                 x86_64          0.9.10-1.el7                        ol7_latest                                25 k
 libXtst                                    x86_64          1.2.3-1.el7                         ol7_latest                                20 k
 libXxf86vm                                 x86_64          1.1.4-1.el7                         ol7_latest                                17 k
 libdrm                                     x86_64          2.4.97-2.el7                        ol7_latest                               151 k
 libglvnd                                   x86_64          1:1.0.1-0.8.git5baa1e5.el7          ol7_latest                                89 k
 libglvnd-egl                               x86_64          1:1.0.1-0.8.git5baa1e5.el7          ol7_latest                                43 k
 libglvnd-glx                               x86_64          1:1.0.1-0.8.git5baa1e5.el7          ol7_latest                               124 k
 libpciaccess                               x86_64          0.14-1.el7                          ol7_latest                                26 k
 libwayland-client                          x86_64          1.15.0-1.el7                        ol7_latest                                32 k
 libwayland-server                          x86_64          1.15.0-1.el7                        ol7_latest                                38 k
 libxcb                                     x86_64          1.13-1.el7                          ol7_latest                               213 k
 libxshmfence                               x86_64          1.2-1.el7                           ol7_latest                               6.5 k
 libxslt                                    x86_64          1.1.28-5.0.1.el7                    ol7_latest                               241 k
 m4                                         x86_64          1.4.16-10.el7                       ol7_latest                               254 k
 mesa-libEGL                                x86_64          18.3.4-6.el7_7                      ol7_latest                               108 k
 mesa-libGL                                 x86_64          18.3.4-6.el7_7                      ol7_latest                               165 k
 mesa-libgbm                                x86_64          18.3.4-6.el7_7                      ol7_latest                                38 k
 mesa-libglapi                              x86_64          18.3.4-6.el7_7                      ol7_latest                                45 k
 patch                                      x86_64          2.7.1-12.el7_7                      ol7_latest                               110 k
 psmisc                                     x86_64          22.20-16.el7                        ol7_latest                               141 k
 redhat-lsb-core                            x86_64          4.1-27.0.1.el7                      ol7_latest                                37 k
 redhat-lsb-submod-security                 x86_64          4.1-27.0.1.el7                      ol7_latest                                15 k
 spax                                       x86_64          1.5.2-13.el7                        ol7_latest                               259 k

Transaction Summary
===============================================================================================================================================
Install  1 Package (+44 Dependent packages)

Total size: 3.2 G
Total download size: 5.8 M
Installed size: 3.2 G
Is this ok [y/d/N]: y
Downloading packages:
(1/44): chrpath-0.16-0.el7.x86_64.rpm                                                                                   |  26 kB  00:00:00
(2/44): avahi-libs-0.6.31-19.el7.x86_64.rpm                                                                             |  61 kB  00:00:00
(3/44): cups-client-1.6.3-40.el7.x86_64.rpm                                                                             | 151 kB  00:00:00
(4/44): dejavu-fonts-common-2.33-6.el7.noarch.rpm                                                                       |  64 kB  00:00:00
(5/44): cups-libs-1.6.3-40.el7.x86_64.rpm                                                                               | 357 kB  00:00:00
(6/44): fontconfig-2.13.0-4.3.el7.x86_64.rpm                                                                            | 254 kB  00:00:00
(7/44): freeglut-3.0.0-8.el7.x86_64.rpm                                                                                 | 185 kB  00:00:00
(8/44): fuse-2.9.4-1.0.4.el7.x86_64.rpm                                                                                 |  86 kB  00:00:00
(9/44): dejavu-sans-fonts-2.33-6.el7.noarch.rpm                                                                         | 1.4 MB  00:00:00
(10/44): fuse-libs-2.9.4-1.0.4.el7.x86_64.rpm                                                                           |  95 kB  00:00:00
(11/44): libICE-1.0.9-9.el7.x86_64.rpm                                                                                  |  66 kB  00:00:00
(12/44): libX11-common-1.6.7-2.el7.noarch.rpm                                                                           | 164 kB  00:00:00
(13/44): libX11-1.6.7-2.el7.x86_64.rpm                                                                                  | 606 kB  00:00:00
(14/44): libXau-1.0.8-2.1.el7.x86_64.rpm                                                                                |  28 kB  00:00:00
(15/44): libXcomposite-0.4.4-4.1.el7.x86_64.rpm                                                                         |  22 kB  00:00:00
(16/44): libXcursor-1.1.15-1.el7.x86_64.rpm                                                                             |  30 kB  00:00:00
(17/44): libXdamage-1.1.4-4.1.el7.x86_64.rpm                                                                            |  20 kB  00:00:00
(18/44): libXext-1.3.3-3.el7.x86_64.rpm                                                                                 |  38 kB  00:00:00
(19/44): libXfixes-5.0.3-1.el7.x86_64.rpm                                                                               |  18 kB  00:00:00
(20/44): libXi-1.7.9-1.el7.x86_64.rpm                                                                                   |  40 kB  00:00:00
(21/44): libXrandr-1.5.1-2.el7.x86_64.rpm                                                                               |  27 kB  00:00:00
(22/44): libXrender-0.9.10-1.el7.x86_64.rpm                                                                             |  25 kB  00:00:00
(23/44): libXtst-1.2.3-1.el7.x86_64.rpm                                                                                 |  20 kB  00:00:00
(24/44): libXxf86vm-1.1.4-1.el7.x86_64.rpm                                                                              |  17 kB  00:00:00
(25/44): libdrm-2.4.97-2.el7.x86_64.rpm                                                                                 | 151 kB  00:00:00
(26/44): libglvnd-1.0.1-0.8.git5baa1e5.el7.x86_64.rpm                                                                   |  89 kB  00:00:00
(27/44): libglvnd-egl-1.0.1-0.8.git5baa1e5.el7.x86_64.rpm                                                               |  43 kB  00:00:00
(28/44): libglvnd-glx-1.0.1-0.8.git5baa1e5.el7.x86_64.rpm                                                               | 124 kB  00:00:00
(29/44): libpciaccess-0.14-1.el7.x86_64.rpm                                                                             |  26 kB  00:00:00
(30/44): libwayland-client-1.15.0-1.el7.x86_64.rpm                                                                      |  32 kB  00:00:00
(31/44): libwayland-server-1.15.0-1.el7.x86_64.rpm                                                                      |  38 kB  00:00:00
(32/44): libxshmfence-1.2-1.el7.x86_64.rpm                                                                              | 6.5 kB  00:00:00
(33/44): libxcb-1.13-1.el7.x86_64.rpm                                                                                   | 213 kB  00:00:00
(34/44): libxslt-1.1.28-5.0.1.el7.x86_64.rpm                                                                            | 241 kB  00:00:00
(35/44): m4-1.4.16-10.el7.x86_64.rpm                                                                                    | 254 kB  00:00:00
(36/44): mesa-libEGL-18.3.4-6.el7_7.x86_64.rpm                                                                          | 108 kB  00:00:00
(37/44): mesa-libGL-18.3.4-6.el7_7.x86_64.rpm                                                                           | 165 kB  00:00:00
(38/44): mesa-libgbm-18.3.4-6.el7_7.x86_64.rpm                                                                          |  38 kB  00:00:00
(39/44): mesa-libglapi-18.3.4-6.el7_7.x86_64.rpm                                                                        |  45 kB  00:00:00
(40/44): patch-2.7.1-12.el7_7.x86_64.rpm                                                                                | 110 kB  00:00:00
(41/44): psmisc-22.20-16.el7.x86_64.rpm                                                                                 | 141 kB  00:00:00
(42/44): redhat-lsb-core-4.1-27.0.1.el7.x86_64.rpm                                                                      |  37 kB  00:00:00
(43/44): redhat-lsb-submod-security-4.1-27.0.1.el7.x86_64.rpm                                                           |  15 kB  00:00:00
(44/44): spax-1.5.2-13.el7.x86_64.rpm                                                                                   | 259 kB  00:00:00
-----------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                           29 MB/s | 5.8 MB  00:00:00
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : mesa-libglapi-18.3.4-6.el7_7.x86_64                                                                                        1/45
  Installing : libxshmfence-1.2-1.el7.x86_64                                                                                              2/45
  Installing : libwayland-server-1.15.0-1.el7.x86_64                                                                                      3/45
  Installing : 1:libglvnd-1.0.1-0.8.git5baa1e5.el7.x86_64                                                                                 4/45
  Installing : avahi-libs-0.6.31-19.el7.x86_64                                                                                            5/45
  Installing : 1:cups-libs-1.6.3-40.el7.x86_64                                                                                            6/45
  Installing : 1:cups-client-1.6.3-40.el7.x86_64                                                                                          7/45
  Installing : fuse-libs-2.9.4-1.0.4.el7.x86_64                                                                                           8/45
  Installing : redhat-lsb-submod-security-4.1-27.0.1.el7.x86_64                                                                           9/45
  Installing : spax-1.5.2-13.el7.x86_64                                                                                                  10/45
  Installing : libXau-1.0.8-2.1.el7.x86_64                                                                                               11/45
  Installing : libxcb-1.13-1.el7.x86_64                                                                                                  12/45
  Installing : chrpath-0.16-0.el7.x86_64                                                                                                 13/45
  Installing : patch-2.7.1-12.el7_7.x86_64                                                                                               14/45
  Installing : psmisc-22.20-16.el7.x86_64                                                                                                15/45
  Installing : libX11-common-1.6.7-2.el7.noarch                                                                                          16/45
  Installing : libX11-1.6.7-2.el7.x86_64                                                                                                 17/45
  Installing : libXext-1.3.3-3.el7.x86_64                                                                                                18/45
  Installing : libXi-1.7.9-1.el7.x86_64                                                                                                  19/45
  Installing : libXrender-0.9.10-1.el7.x86_64                                                                                            20/45
  Installing : libXfixes-5.0.3-1.el7.x86_64                                                                                              21/45
  Installing : libXxf86vm-1.1.4-1.el7.x86_64                                                                                             22/45
  Installing : libXcursor-1.1.15-1.el7.x86_64                                                                                            23/45
  Installing : libXdamage-1.1.4-4.1.el7.x86_64                                                                                           24/45
  Installing : libXrandr-1.5.1-2.el7.x86_64                                                                                              25/45
  Installing : libXtst-1.2.3-1.el7.x86_64                                                                                                26/45
  Installing : libXcomposite-0.4.4-4.1.el7.x86_64                                                                                        27/45
  Installing : dejavu-fonts-common-2.33-6.el7.noarch                                                                                     28/45
  Installing : dejavu-sans-fonts-2.33-6.el7.noarch                                                                                       29/45
  Installing : fontconfig-2.13.0-4.3.el7.x86_64                                                                                          30/45
  Installing : libxslt-1.1.28-5.0.1.el7.x86_64                                                                                           31/45
  Installing : fuse-2.9.4-1.0.4.el7.x86_64                                                                                               32/45
  Installing : libwayland-client-1.15.0-1.el7.x86_64                                                                                     33/45
  Installing : libICE-1.0.9-9.el7.x86_64                                                                                                 34/45
  Installing : m4-1.4.16-10.el7.x86_64                                                                                                   35/45
  Installing : redhat-lsb-core-4.1-27.0.1.el7.x86_64                                                                                     36/45
  Installing : libpciaccess-0.14-1.el7.x86_64                                                                                            37/45
  Installing : libdrm-2.4.97-2.el7.x86_64                                                                                                38/45
  Installing : 1:libglvnd-glx-1.0.1-0.8.git5baa1e5.el7.x86_64                                                                            39/45
  Installing : mesa-libGL-18.3.4-6.el7_7.x86_64                                                                                          40/45
  Installing : freeglut-3.0.0-8.el7.x86_64                                                                                               41/45
  Installing : mesa-libgbm-18.3.4-6.el7_7.x86_64                                                                                         42/45
  Installing : 1:libglvnd-egl-1.0.1-0.8.git5baa1e5.el7.x86_64                                                                            43/45
  Installing : mesa-libEGL-18.3.4-6.el7_7.x86_64                                                                                         44/45
This system meets or exceeds the minimum recommended Tableau Server requirements
  Installing : tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64                                                               45/45
Creating /usr/lib64/libcrypt.so (a workaround for some RHEL 7-based installations)

If this is a single node or initial node installation, run:

    sudo /opt/tableau/tableau_server/packages/scripts.20201.20.0305.1738/initialize-tsm --accepteula

to continue setting up Tableau Server. If this installation is part of a multi-node configuration,
see the online documentation for installing Tableau Server on additional nodes.

  Verifying  : libXext-1.3.3-3.el7.x86_64                                                                                                 1/45
  Verifying  : libpciaccess-0.14-1.el7.x86_64                                                                                             2/45
  Verifying  : libXi-1.7.9-1.el7.x86_64                                                                                                   3/45
  Verifying  : fontconfig-2.13.0-4.3.el7.x86_64                                                                                           4/45
  Verifying  : libXrender-0.9.10-1.el7.x86_64                                                                                             5/45
  Verifying  : 1:libglvnd-glx-1.0.1-0.8.git5baa1e5.el7.x86_64                                                                             6/45
  Verifying  : libXxf86vm-1.1.4-1.el7.x86_64                                                                                              7/45
  Verifying  : redhat-lsb-core-4.1-27.0.1.el7.x86_64                                                                                      8/45
  Verifying  : libXcursor-1.1.15-1.el7.x86_64                                                                                             9/45
  Verifying  : m4-1.4.16-10.el7.x86_64                                                                                                   10/45
  Verifying  : libICE-1.0.9-9.el7.x86_64                                                                                                 11/45
  Verifying  : mesa-libGL-18.3.4-6.el7_7.x86_64                                                                                          12/45
  Verifying  : 1:cups-client-1.6.3-40.el7.x86_64                                                                                         13/45
  Verifying  : libwayland-client-1.15.0-1.el7.x86_64                                                                                     14/45
  Verifying  : avahi-libs-0.6.31-19.el7.x86_64                                                                                           15/45
  Verifying  : fuse-2.9.4-1.0.4.el7.x86_64                                                                                               16/45
  Verifying  : mesa-libEGL-18.3.4-6.el7_7.x86_64                                                                                         17/45
  Verifying  : libxslt-1.1.28-5.0.1.el7.x86_64                                                                                           18/45
  Verifying  : dejavu-fonts-common-2.33-6.el7.noarch                                                                                     19/45
  Verifying  : libXcomposite-0.4.4-4.1.el7.x86_64                                                                                        20/45
  Verifying  : libXtst-1.2.3-1.el7.x86_64                                                                                                21/45
  Verifying  : libX11-1.6.7-2.el7.x86_64                                                                                                 22/45
  Verifying  : libX11-common-1.6.7-2.el7.noarch                                                                                          23/45
  Verifying  : libxcb-1.13-1.el7.x86_64                                                                                                  24/45
  Verifying  : libdrm-2.4.97-2.el7.x86_64                                                                                                25/45
  Verifying  : psmisc-22.20-16.el7.x86_64                                                                                                26/45
  Verifying  : 1:libglvnd-1.0.1-0.8.git5baa1e5.el7.x86_64                                                                                27/45
  Verifying  : patch-2.7.1-12.el7_7.x86_64                                                                                               28/45
  Verifying  : tableau-server-20201.20.0305.1738-20201-20.0305.1738.x86_64                                                               29/45
  Verifying  : libXdamage-1.1.4-4.1.el7.x86_64                                                                                           30/45
  Verifying  : mesa-libgbm-18.3.4-6.el7_7.x86_64                                                                                         31/45
  Verifying  : 1:cups-libs-1.6.3-40.el7.x86_64                                                                                           32/45
  Verifying  : dejavu-sans-fonts-2.33-6.el7.noarch                                                                                       33/45
  Verifying  : libXrandr-1.5.1-2.el7.x86_64                                                                                              34/45
  Verifying  : mesa-libglapi-18.3.4-6.el7_7.x86_64                                                                                       35/45
  Verifying  : chrpath-0.16-0.el7.x86_64                                                                                                 36/45
  Verifying  : libwayland-server-1.15.0-1.el7.x86_64                                                                                     37/45
  Verifying  : libxshmfence-1.2-1.el7.x86_64                                                                                             38/45
  Verifying  : libXau-1.0.8-2.1.el7.x86_64                                                                                               39/45
  Verifying  : 1:libglvnd-egl-1.0.1-0.8.git5baa1e5.el7.x86_64                                                                            40/45
  Verifying  : spax-1.5.2-13.el7.x86_64                                                                                                  41/45
  Verifying  : redhat-lsb-submod-security-4.1-27.0.1.el7.x86_64                                                                          42/45
  Verifying  : fuse-libs-2.9.4-1.0.4.el7.x86_64                                                                                          43/45
  Verifying  : libXfixes-5.0.3-1.el7.x86_64                                                                                              44/45
  Verifying  : freeglut-3.0.0-8.el7.x86_64                                                                                               45/45

Installed:
  tableau-server-20201.20.0305.1738.x86_64 0:20201-20.0305.1738

Dependency Installed:
  avahi-libs.x86_64 0:0.6.31-19.el7                  chrpath.x86_64 0:0.16-0.el7                cups-client.x86_64 1:1.6.3-40.el7
  cups-libs.x86_64 1:1.6.3-40.el7                    dejavu-fonts-common.noarch 0:2.33-6.el7    dejavu-sans-fonts.noarch 0:2.33-6.el7
  fontconfig.x86_64 0:2.13.0-4.3.el7                 freeglut.x86_64 0:3.0.0-8.el7              fuse.x86_64 0:2.9.4-1.0.4.el7
  fuse-libs.x86_64 0:2.9.4-1.0.4.el7                 libICE.x86_64 0:1.0.9-9.el7                libX11.x86_64 0:1.6.7-2.el7
  libX11-common.noarch 0:1.6.7-2.el7                 libXau.x86_64 0:1.0.8-2.1.el7              libXcomposite.x86_64 0:0.4.4-4.1.el7
  libXcursor.x86_64 0:1.1.15-1.el7                   libXdamage.x86_64 0:1.1.4-4.1.el7          libXext.x86_64 0:1.3.3-3.el7
  libXfixes.x86_64 0:5.0.3-1.el7                     libXi.x86_64 0:1.7.9-1.el7                 libXrandr.x86_64 0:1.5.1-2.el7
  libXrender.x86_64 0:0.9.10-1.el7                   libXtst.x86_64 0:1.2.3-1.el7               libXxf86vm.x86_64 0:1.1.4-1.el7
  libdrm.x86_64 0:2.4.97-2.el7                       libglvnd.x86_64 1:1.0.1-0.8.git5baa1e5.el7 libglvnd-egl.x86_64 1:1.0.1-0.8.git5baa1e5.el7
  libglvnd-glx.x86_64 1:1.0.1-0.8.git5baa1e5.el7     libpciaccess.x86_64 0:0.14-1.el7           libwayland-client.x86_64 0:1.15.0-1.el7
  libwayland-server.x86_64 0:1.15.0-1.el7            libxcb.x86_64 0:1.13-1.el7                 libxshmfence.x86_64 0:1.2-1.el7
  libxslt.x86_64 0:1.1.28-5.0.1.el7                  m4.x86_64 0:1.4.16-10.el7                  mesa-libEGL.x86_64 0:18.3.4-6.el7_7
  mesa-libGL.x86_64 0:18.3.4-6.el7_7                 mesa-libgbm.x86_64 0:18.3.4-6.el7_7        mesa-libglapi.x86_64 0:18.3.4-6.el7_7
  patch.x86_64 0:2.7.1-12.el7_7                      psmisc.x86_64 0:22.20-16.el7               redhat-lsb-core.x86_64 0:4.1-27.0.1.el7
  redhat-lsb-submod-security.x86_64 0:4.1-27.0.1.el7 spax.x86_64 0:1.5.2-13.el7

Complete!

```

### Start TSM

Start TSM:
```
[opc@frdeng-tabsvr ~]$ cd /opt/tableau/tableau_server/packages/scripts.20201.20.0305.1738/
[opc@frdeng-tabsvr scripts.20201.20.0305.1738]$ sudo ./initialize-tsm --accepteula
Creating directories and setting permissions...
Using '/var/opt/tableau/tableau_server' as the data directory.
Adding user 'opc' to group 'tableau'...
Adding user 'opc' to group 'tsmadmin'...
Added. Note: These group membership changes do not take effect in shells already open. For these to take effect, log out of the shell and log back in.
Tableau Server runs best with at least 50 GB of free disk space,
but found only 30 GB for the data directory '/var/opt/tableau/tableau_server'. Continuing.
Creating environment file...
Starting TSM services...
Updating repository version in Tableau Server Coordination Service.
TSM services started successfully
Use the 'tsm' command to continue setting up Tableau Server.
>> Tableau binary directory will be added to PATH for new shells. To get the
>> updated path, either start a new session, or for bash users run:
>> source /etc/profile.d/tableau_server.sh
The TSM administrative web interface (and REST API) is now available at
https://frdeng-tabsvr:8850
You can continue the configuration and initialization of Tableau server using either the TSM command line interface,
or the web interface.
You will be prompted to authenticate, or can log in using the username 'opc', with the same password you used to log into this session. You could also use any username, with its password, from the administrative group in the domain.
Done.
```

Add an admin user to group tsmadmin, and set password
```
opc@frdeng-tabsvr ~]$ sudo useradd -G tsmadmin tsm
[opc@frdeng-tabsvr ~]$ id tsm
uid=1001(tsm) gid=1001(tsm) groups=1001(tsm),991(tsmadmin)
[opc@frdeng-tabsvr ~]$ sudo passwd tsm
Changing password for user tsm.
New password:
Retype new password:
passwd: all authentication tokens updated successfully.
```

### TSM Web UI

If you run tableau server on public cloud, you need to add a security or firewall ingress rule to open port 8850 first.

Go to TSM web UI in browser:
```
https://<compute instance IP>:8850
```
Log in with the user `tsm`

Enter the product key if you have, or "Start Tableau Server Trial"

Register

Setup

Inititialize

### Add Tableau server administrator account
```
[opc@frdeng-tabsvr ~]$ tabcmd initialuser --server http://localhost --username 'tableau-admin'
Password:
===== redirecting to http://localhost/auth
===== Signed out
===== Creating new session
=====     Server:   http://localhost
=====     Username: tableau-admin
===== Connecting to the server...
===== Signing in...
===== Succeeded
```

### Tableau Web UI

If you run tableau server on public cloud, you need to add a security or firewall ingress rule to open port 80 first.

Got to Tableau Web UI
```
http://129.146.72.47/
```
Log in with administrator `tableau-admin`


### Post installation tasks
 - Security hardening
 - SMTP
 - Files and permission for TSM
 - Server event notification
 - Data Cache
 - Database driver
 - Server crash reporter

### Tableau server processes
```
pstree
        ├─systemd─┬─(sd-pam)
        │         ├─FNPLicensingSer───{FNPLicensingSer}
        │         ├─FNPLicensingSer
        │         ├─appzookeeper───92*[{appzookeeper}]
        │         ├─clientfileservi───89*[{clientfileservi}]
        │         ├─hyperd───154*[{hyperd}]
        │         ├─java───208*[{java}]
        │         ├─java───239*[{java}]
        │         ├─java───130*[{java}]
        │         ├─lmgrd───{lmgrd}
        │         ├─nlp───90*[{nlp}]
        │         ├─2*[redis-server───2*[{redis-server}]]
        │         ├─run-apigateway───88*[{run-apigateway}]
        │         ├─run-backgrounde───251*[{run-backgrounde}]
        │         ├─run-backgrounde───325*[{run-backgrounde}]
        │         ├─run-clustercont─┬─postgres───32*[postgres]
        │         │                 └─128*[{run-clustercont}]
        │         ├─2*[run-dataserver───245*[{run-dataserver}]]
        │         ├─run-filestore───116*[{run-filestore}]
        │         ├─run-flowprocess─┬─prepservice─┬─tdeserver64───74*[{tdeserver64}]
        │         │                 │             └─156*[{prepservice}]
        │         │                 └─115*[{run-flowprocess}]
        │         ├─run-gateway─┬─httpd───3*[httpd───65*[{httpd}]]
        │         │             └─141*[{run-gateway}]
        │         ├─run-interactive───165*[{run-interactive}]
        │         ├─run-noninteract───127*[{run-noninteract}]
        │         ├─run-tdsservice───152*[{run-tdsservice}]
        │         ├─run-vizportal───436*[{run-vizportal}]
        │         ├─4*[run-vizqlserver───445*[{run-vizqlserver}]]
        │         ├─run-webhooks───144*[{run-webhooks}]
        │         ├─tabadminagent───254*[{tabadminagent}]
        │         ├─tabadmincontrol───199*[{tabadmincontrol}]
        │         └─tdsservice───7*[{tdsservice}]
```
 - FNPLicensingSer
 - appzookeeper
 - clientfileservi
 - hyperd
 - lmgrd
 - nlp
 - redis-server x 2
 - run-apigateway
 - run-backgrounde x 2
 - run-clustercont
   * postgres
 - run-dataserver x 2
 - run-filestore
 - run-flowprocess
   * prepservice
     - tdeserver64
 - run-gateway
   * httpd
 - run-interactive
 - run-noninteract
 - run-vizportal x 4
 - run-vizqlserver
 - run-webhooks
 - tabadminagent
 - tabadmincontrol

```
[opc@frdeng-tabsvr ~]$ ps -u tableau
   PID TTY          TIME CMD
  5319 ?        00:00:01 systemd
  5322 ?        00:00:00 (sd-pam)
  5922 ?        00:00:00 FNPLicensingSer
  5928 ?        00:00:00 FNPLicensingSer
  6180 ?        00:00:14 appzookeeper
  6561 ?        00:00:00 lmgrd
  6600 ?        00:00:11 clientfileservi
  7188 ?        00:02:48 tabadmincontrol
  7484 ?        00:01:37 tabadminagent
 54250 ?        00:00:36 run-clustercont
 54325 ?        00:02:18 java
 54556 ?        00:00:48 java
 55055 ?        00:00:00 postgres
 55060 ?        00:00:00 postgres
 55064 ?        00:00:00 postgres
 55065 ?        00:00:00 postgres
 55066 ?        00:00:00 postgres
 55067 ?        00:00:00 postgres
 55068 ?        00:00:00 postgres
 55069 ?        00:00:00 postgres
 57521 ?        00:03:36 run-interactive
 57525 ?        00:04:55 run-noninteract
 57844 ?        00:04:20 run-vizqlserver
 57848 ?        00:00:21 java
 57851 ?        00:00:14 run-filestore
 57853 ?        00:02:01 run-flowprocess
 57855 ?        00:04:23 run-vizqlserver
 57864 ?        00:00:03 tdsservice
 57872 ?        00:03:56 run-dataserver
 57888 ?        00:01:11 run-apigateway
 57913 ?        00:03:58 run-vizqlserver
 57933 ?        00:01:11 run-gateway
 57968 ?        00:02:04 run-webhooks
 57995 ?        00:00:06 hyperd
 58031 ?        00:00:01 redis-server
 58055 ?        00:03:41 run-backgrounde
 58100 ?        00:03:46 run-dataserver
 58125 ?        00:07:00 run-vizportal
 58130 ?        00:01:01 run-tdsservice
 58143 ?        00:04:22 run-vizqlserver
 58196 ?        00:00:01 redis-server
 60180 ?        00:00:00 httpd
 60183 ?        00:00:00 httpd
 60184 ?        00:00:00 httpd
 60185 ?        00:00:00 httpd
 60466 ?        00:00:00 postgres
 60467 ?        00:00:00 postgres
 60493 ?        00:00:00 postgres
 60618 ?        00:00:05 prepservice
 60744 ?        00:00:00 postgres
 60746 ?        00:00:01 postgres
 60870 ?        00:00:00 tdeserver64
 61182 ?        00:00:01 postgres
 61629 ?        00:00:00 postgres
 61637 ?        00:00:00 postgres
 62957 ?        00:00:00 postgres
 62959 ?        00:00:00 postgres
 63146 ?        00:00:00 postgres
 63792 ?        00:00:00 postgres
 63793 ?        00:00:00 postgres
 63794 ?        00:00:00 postgres
 63798 ?        00:00:00 postgres
 63799 ?        00:00:00 postgres
 63800 ?        00:00:00 postgres
 63884 ?        00:00:00 postgres
 63885 ?        00:00:00 postgres
 63886 ?        00:00:00 postgres
 63900 ?        00:03:20 run-backgrounde
 65292 ?        00:00:32 nlp
 65757 ?        00:00:00 postgres
 65761 ?        00:00:02 postgres
 65766 ?        00:00:02 postgres
 66006 ?        00:00:00 postgres
 66007 ?        00:00:00 postgres
```
### Tableau server pacakges

/opt/tableau/tableau_server/packages

```
activemq.20201.20.0305.1738
activemqserver.20201.20.0305.1738
apache.20201.20.0305.1738
apigateway.20201.20.0305.1738
appzookeeper.20201.20.0305.1738
authnservice.20201.20.0305.1738
bin.20201.20.0305.1738
cacheserver.20201.20.0305.1738
clientfileservice.20201.20.0305.1738
clustercontroller.20201.20.0305.1738
contentexploration.20201.20.0305.1738
contentfavorites.20201.20.0305.1738
contentmodel.20201.20.0305.1738
contentprovider.20201.20.0305.1738
controlsimpleservice.20201.20.0305.1738
crashreporting.20201.20.0305.1738
customer-bin.20201.20.0305.1738
databasemaintenance.20201.20.0305.1738
docs.20201.20.0305.1738
elasticsearch.20201.20.0305.1738
elasticserver.20201.20.0305.1738
extcontentprovider.20201.20.0305.1738
extensionsserver.20201.20.0305.1738
filestore.20201.20.0305.1738
floweditor.20201.20.0305.1738
flowprocessor.20201.20.0305.1738
flowprovider.20201.20.0305.1738
flowqueryservice.20201.20.0305.1738
gateway.20201.20.0305.1738
geodatabase.20201.20.0305.1738
hyper.20201.20.0305.1738
hypercontrol.20201.20.0305.1738
installer.20201.20.0305.1738
interactive.20201.20.0305.1738
lib.20201.20.0305.1738
managementlibs.20201.20.0305.1738
metrics.20201.20.0305.1738
metricsedge.20201.20.0305.1738
nlp.20201.20.0305.1738
noninteractive.20201.20.0305.1738
pacs.20201.20.0305.1738
pgsql.20201.20.0305.1738
pgsqlcontrol.20201.20.0305.1738
profiler.20201.20.0305.1738
publishedconnections.20201.20.0305.1738
querygateway.20201.20.0305.1738
recommendations.20201.20.0305.1738
redis.20201.20.0305.1738
relationshipingestor.20201.20.0305.1738
relationshipservice.20201.20.0305.1738
repository.20201.20.0305.1738
samlservice.20201.20.0305.1738
scripts.20201.20.0305.1738
searchserver.20201.20.0305.1738
sentry.20201.20.0305.1738
solr7.20201.20.0305.1738
sos.20201.20.0305.1738
tabadminagent.20201.20.0305.1738
tabsvc.20201.20.0305.1738
tde.20201.20.0305.1738
tdecontrol.20201.20.0305.1738
tdsnativeservice.20201.20.0305.1738
tdsservice.20201.20.0305.1738
templates.20201.20.0305.1738
tomcat.20201.20.0305.1738
tomcatcontainer.20201.20.0305.1738
tomcat-tablib.20201.20.0305.1738
vizportalclient.20201.20.0305.1738
vizqlserver.20201.20.0305.1738
webclients.20201.20.0305.1738
webhooks.20201.20.0305.1738
wgserver.20201.20.0305.1738
zookeeper.20201.20.0305.1738
```

### /etc configuration files
```
/etc/security/limits.d/99-tableau_server_"${version_string}".conf
/etc/systemd/logind.conf.d/tableau_server_"${version_string}".conf
/etc/systemd/system/user-.slice.d/tableau_server_"${version_string}".conf
```

### Tablea for Kubernetes
discussion - https://community.tableau.com/ideas/9630


