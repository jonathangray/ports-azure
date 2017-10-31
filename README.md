
#  azure-cli and other utils for OpenBSD

This repo contains the essential files needed to operate Microsoft Azure from OpenBSD (e.g.: azure-cli). 
This toolset also allows the creation of OpenBSD VMs that can later be imported to Azure using the scripts under
[reyk/cloud-openbsd](https://github.com/reyk/cloud-openbsd). 

## References

[Command-line tools for Azure on GitHub](https://github.com/Azure/azure-cli)

[Usage documentation](https://docs.microsoft.com/en-us/cli/azure/)

## Prerequisites

* shell access to OpenBSD 6.1
* The following packages installed: git, python, qemu

## Download and Extract ports-azure

Download or fetch the `ports-azure` repo and extract it to /usr/ports.

```
$ ftp -o ports-azure.zip https://github.com/jonathangray/ports-azure/archive/master.zip
$ unzip ports-azure.zip
```
Next, move the ports-azure-master to the right directory (/usr/ports)

```
$ doas mv ports-azure-master /usr/ports/ports-azure
```

## Prepare for the build process

We will instruct the ports infrastructure that we now have a new directory with new ports to be 
built. 

change mk.conf to have

```
PORTSDIR_PATH=${PORTSDIR}:${PORTSDIR}/ports-azure
```
 
> Optionally, to make the build faster, you can add the following to mk.conf:

```
FETCH_PACKAGES=yes
```
## Building the toolset

The first tool we will build will be `azure-cli`, which can be found under `/usr/ports/ports-azure/sysutils/azure-cli`.

```
cd /usr/ports/ports-azure/sysutils/azure-cli
```
For the build to work, you will have to create a checksum of the files.

```
$ doas make makesum                                                    
doas (dcasati@puffy.dcvlab.home) password: 
===>  Checking files for azure-cli-2.0.0p0
>> Fetch https://github.com/Azure/azure-cli/archive/6cd5d7c924b9674b4729cd8316aad1ce72b052d3.tar.gz
$
```

then proceed with `make` and `make install`.
```
$ doas make
doas (dcasati@puffy.dcvlab.home) password: 
===> azure-cli-2.0.0p0 depends on: py-setuptools-* -> py-setuptools-28.6.1p0v0
===> azure-cli-2.0.0p0 depends on: python->=2.7,<2.8 -> python-2.7.14
===>  Checking files for azure-cli-2.0.0p0
`/usr/ports/distfiles/azure-cli-all-20170228-6cd5d7c9.tar.gz' is up to date.
>> (SHA256) azure-cli-all-20170228-6cd5d7c9.tar.gz: OK
===>  Extracting for azure-cli-2.0.0p0
sed -i -e 's,/bin/bash,/usr/local/bin/bash,' /usr/ports/pobj/azure-cli-2.0.0/azure-cli-6cd5d7c924b9674b4729cd8316aad1ce72b052d3/src/azure-cli/az
sed -i -e "s,^python,/usr/local/bin/python2.7," /usr/ports/pobj/azure-cli-2.0.0/azure-cli-6cd5d7c924b9674b4729cd8316aad1ce72b052d3/src/azure-cli/az
===>  Patching for azure-cli-2.0.0p0
===>  Compiler link: clang -> /usr/bin/clang
===>  Compiler link: clang++ -> /usr/bin/clang++
===>  Compiler link: cc -> /usr/bin/cc
===>  Compiler link: c++ -> /usr/bin/c++
===>  Configuring for azure-cli-2.0.0p0
===>  Building for azure-cli-2.0.0p0
$ doas make install
```
Now install `azure-vhd-utils` found under sysutils/azure-vhd-utils.

```
cd /usr/ports/ports-azure/sysutils/azure-vhd-utils
```

Run `make makesum` and proceed with the build.

```
$ doas make makesum    
doas (dcasati@puffy.dcvlab.home) password: 
===>  Checking files for azure-vhd-utils-20170104
>> Fetch https://github.com/Microsoft/azure-vhd-utils/archive/2dd43d88c85c06c55828c86159d4583db9d41fbb.tar.gz
```
You can now make the port.

```
$ doas make                                                                                         
doas (dcasati@puffy.dcvlab.home) password:                                                          
===> azure-vhd-utils-20170104 depends on: go-=1.9 -> go-1.9
===>  Verifying specs:  c pthread                            
===>  found c.90.0 pthread.24.0        
===>  Checking files for azure-vhd-utils-20170104                                                   
`/usr/ports/distfiles/azure-vhd-utils-20170104-2dd43d88.tar.gz' is up to date.
>> (SHA256) azure-vhd-utils-20170104-2dd43d88.tar.gz: OK     
===>  Extracting for azure-vhd-utils-20170104                                                       
===>  Patching for azure-vhd-utils-20170104                                             
===>  Compiler link: clang -> /usr/bin/clang
===>  Compiler link: clang++ -> /usr/bin/clang++
===>  Compiler link: cc -> /usr/bin/cc
===>  Compiler link: c++ -> /usr/bin/c++
===>  Configuring for azure-vhd-utils-20170104
===>  Building for azure-vhd-utils-20170104

[...]

$
```

## Notes

There seems to be some kind of strange packaging error on microsoft's part
as python modules can sometimes not be found at build time with

```
warning: no previously-included files found matching 'azure/__init__.py'
warning: no previously-included files found matching 'azure/mgmt/__init__.py'
```
<https://github.com/Azure/azure-storage-python/issues/51>

Ports that need these to build have this worked around by symlinking
the files into WRKSRC.

They come from

```
devel/py-azure-nspkg            azure/__init__.py
devel/py-azure-mgmt-nspkg       azure/mgmt/__init__.py
```

The latest py-azure-mgmt-resource 0.31.0 is not compatible 0.30.2 must
be used as 0.30.2 removes a file used by py-azure-cli-resource.
