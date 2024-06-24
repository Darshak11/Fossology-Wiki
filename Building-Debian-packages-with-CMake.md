## Using CPack for building packages

The Debian packages can be built using the [CPack's DEB generator](https://cmake.org/cmake/help/latest/cpack_gen/deb.html). Due to it's limited abilities, the minimum version of CMake required is 3.19.0 and it can be installed from https://cmake.org/download/.

Since FOSSology historically used different paths for installation, they need to be configured while configuring CMake using variables. If CMake is already configured on the system, it is advised to remove the binary directory and reconfigure it.

```console
$ rm -rf ./build
```

### Configuring CMake

Make sure the step 1 from [Install from Source](https://github.com/fossology/fossology/wiki/Install-from-Source#1-install-dependencies) is done to install all build dependencies.

This configuration should **only used for Debian packaging** and not for **source install**.

**Note:** The install prefix and other folder locations are changed for Debian packages.

```console
$ cmake -DCMAKE_BUILD_TYPE=Release \
  -DCMAKE_INSTALL_PREFIX=/usr -DFO_SYSCONFDIR=/etc/fossology -DFO_LOCALSTATEDIR=/var \
  -S. -B./build -G Ninja
```

### Build packages

The packaging process can easily be triggered from ninja using following command:

```console
$ ninja -C ./build package
```

The packages will be available under `./build` directory ending with `.deb` extension. If required, the debugging symbol packages can be removed using `find build -type f -name "*-dbgsym*" -delete`.

All packages can be tarred using

```console
$ mkdir -p packages
$ mv build/*.deb packages/
$ tar -czvf fossology-debian.tar.gz packages
```

## Adding new packages
To add new packages to fossology, modify the file `cmake/FoPackaging.cmake`.
1. Add the CMake component name to `CPACK_COMPONENTS_ALL` list.
1. Create the package variables (replace the `<>` placeholders following the upper/lower case)

```
## FOSSOLOGY-<COMPONENT> PACKAGE
set(CPACK_DEBIAN_FOSSOLOGY-<COMPONENT>_PACKAGE_NAME "fossology-<component>")
set(CPACK_DEBIAN_FOSSOLOGY-<COMPONENT>_FILE_NAME "fossology-<component>_${FO_PACKAGE_VERSION}-1_amd64.deb")
set(CPACK_DEBIAN_FOSSOLOGY-<COMPONENT>_DESCRIPTION
"architecture for analyzing software, <component_info>
${FO_PACKAGE_COMMON_DESCRIPTION}
<component_description>.")

set(CPACK_DEBIAN_FOSSOLOGY-<COMPONENT>_PACKAGE_DEPENDS
    "php7.2-pgsql | php7.3-pgsql | php7.4-pgsql | php8.1-pgsql, <component_dependency>") # Remove if not required

set(CPACK_DEBIAN_FOSSOLOGY-<COMPONENT>_PACKAGE_SECTION "utils")
set(CPACK_DEBIAN_FOSSOLOGY-<COMPONENT>_PACKAGE_CONTROL_EXTRA
"${FO_DEBDIR}/common/postinst;${FO_DEBDIR}/common/postrm;${FO_DEBDIR}/common/conffiles") # Remove if not required
```