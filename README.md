[Command-line tools for Azure on GitHub](https://github.com/Azure/azure-cli)

[Usage documentation](https://docs.microsoft.com/en-us/cli/azure/)

To use extract in /usr/ports/port-azure

change mk.conf to have

`PORTSDIR_PATH=${PORTSDIR}:${PORTSDIR}/ports-azure`

And install sysutils/azure-cli

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
