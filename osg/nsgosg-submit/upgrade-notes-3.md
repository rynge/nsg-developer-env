2023/05/02

Upgrading HTCondor and other OSG packages on nsgosg.sdsc.edu after recently running into an authentication problem to the OSPool. In addition to the following upgrades, we were issued a new ospool.token that should support 'capabilities' in HTCondor.

```
[mkandes@nsgosg ~]$ condor_q --version
$CondorVersion: 9.0.17 Oct 04 2022 PackageID: 9.0.17-1.1 $
$CondorPlatform: X86_64-Rocky_8.6 $
[mkandes@nsgosg ~]$
```

```
[mkandes@nsgosg ~]$ yum repolist enabled
repo id                 repo name
SDSC-AppStream          Rocky Linux 8 AppStream
SDSC-BaseOS             Rocky Linux 8 BaseOS
SDSC-extras             Rocky Linux 8 extras
duosecurity             Duo Security Repository
epel                    Extra Packages for Enterprise Linux 8 - x86_64
osg                     OSG Software for Enterprise Linux 8 - x86_64
[mkandes@nsgosg ~]$
```