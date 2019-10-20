 # 升级centos ImageMagick 到最新版本
 
```
由于CentOS7默认安装的ImageMagick 版本很多新特性以及文件MIME无法识别,使用remi源升级到最新版本.
```
 
## 安装epel库
安装CentOS SCLo RH存储库：  
epel是社区强烈打造的免费开源发行软件包版本库。  
EPEL，即Extra Packages for Enterprise Linux的简称，是为企业级Linux提供的一组高质量的额外软件包，包括但不限于Red Hat Enterprise Linux (RHEL), CentOS and Scientific Linux (SL), Oracle Enterprise Linux (OEL)。(关于 : EPEL)

```shell
yum -y install epel-release
```

## 安装REMI 库  
EPEL有“ 额外的企业版Linux软件包“ 库，有很多这是不在官方软件仓库添加额外的软件包。 REMI是第三方库提供的最新版本，其中已经包含在CentOS和Red Hat的官方软件仓库包。 本文将帮助您安装 EPEL和 REMI库在CentOS和Red Hat 7/6/5系统。

```shell
yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm -y
```

## 安装yum-utils库

```shell
yum install yum-utils -y
```

## 移除已安装的ImageMagick

```shell
yum remove ImageMagick -y
```

## 安装最新版ImageMagick

```shell
yum --enablerepo=remi install ImageMagick7 -y
```
