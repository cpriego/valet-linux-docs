[Main page](index)

# Requirements
- [Ubuntu](#ubuntu)
    - [Ubuntu 14.04](#1404)
    - [Supported versions](#ubuntu-suported-versions)
- [Fedora](#fedora)
    - [SELinux](#selinux)
- [Arch Linux](#arch)
- [Regarding sudo and root user](#sudo)

## <a name="ubuntu">Ubuntu (and derivates)</a>

Requirement | Description
------------- | -------------
Ubuntu version | 14.04+
OS packages | `sudo apt-get install network-manager libnss3-tools jq xsel`
PHP version | 5.6+
PHP extensions | `php*-cli php*-curl php*-mbstring php*-mcrypt php*-xml php*-zip`
Optional packages | `php*-sqlite3 php*-mysql php*-pgsql`

_Replace the star **\*** with your php version._

<a name="1404"></a>
### Ubuntu 14.04

In order to use the `valet secure` command in Ubuntu **14.04** you need to add the nginx PPA because the version in the Trusty repos does not support `http2`.

To add the nginx ppa:
```
sudo add-apt-repository -y ppa:nginx/stable
sudo apt-get update
```

<a name="ubuntu-supported-versions"></a>
### Suported Ubuntu versions
 - LTS: Will get 4 year support (meaning only the latest 2 releases).
 - Non-LTS: Only get 9 months. You *should* update anyway.
 - Development: Only if I have the time. Development version are extremely unstable and prone to change. It is **very** difficult to isolate any issue.

-----
## <a name="fedora">Fedora (and derivates)</a>

Requirement | Description
------------- | -------------
Fedora version | 24+
OS packages | `dnf install nss-tools jq xsel`
PHP version | 5.6+
PHP extensions | `dnf install php-{cli,process,mbstring,mcrypt,xml}`
Optional packages | `sqlite3, mysql, pgsql`

<a name="selinux"></a>
### Regarding SELinux

Fedora users are *expected* to have knowledge of SELinux and how to configure or disable it while Valet makes changes to the system files, otherwise you will receive errors about changes that could not be made.

The easiest way is to set SELinux in Permissive mode.

#### How to set SELinux in Permissive Mode

Temporarily (until reboot): `sudo setenforce 0`

Permanent:
 - Open `/etc/selinux/config`
 - Change `SELINUX=enforcing` to `SELINUX=permissive`
 - Reboot

-----
## <a name="arch">Arch (and derivates)</a>

Requirement | Description
------------- | -------------
OS packages | `pacman -S nss jq xsel networkmanager`
PHP version | `pacman -S php` ( need **>= 5.6** ; check version with `php -v` after installing)
PHP extensions | `php-mcrypt` ( `php` package comes with a lot of compiled in modules. Including `cli, curl, mbstring, xml, zip`. If you don't find an extension, it could be that it is now a part of the `php` package. To check compiled in modules run `php -m`)
Optional packages | [php-sqlite](https://wiki.archlinux.org/index.php/PHP#Sqlite), [mysql/mariadb](https://wiki.archlinux.org/index.php/PHP#MySQL.2FMariaDB), [php-pgsql](https://wiki.archlinux.org/index.php/PHP#PostgreSQL)
Composer | Install [composer](https://wiki.archlinux.org/index.php/PHP#Composer), php package manager

-----
## <a name="sudo">Regarding `sudo` and `root` user</a>

Valet makes automatic use of **`sudo`** to perform some of its tasks. This implies that for Valet to perform correctly your user needs to be configured as a **sudo** user.

Please **do not, under any circumstance, install valet with `root` or the `sudo` command**. Kittens could die.
