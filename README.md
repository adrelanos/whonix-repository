# Whonix APT Repository Tool #

This tool can always be used to enable either Whonix's stable, testers or
developers repository or to disable Whonix's repository.

Whonix's APT Repository is not enabled by default. Some users prefer this for
trust/security reasons.

On first boot of Whonix, the Whonix Repository Tool gets automatically started
by whonixsetup. The user is free to either leave Whonix's repository disabled
or to configure it as desired.

Technically speaking, this tool creates or deletes
/etc/sources.list.d/whonix.list and adds or deletes Whonix's signing key from
apt-key.
## How to install `whonix-repository` using apt-get ##

1\. Download [Whonix's Signing Key]().

```
wget https://www.whonix.org/patrick.asc
```

Users can [check Whonix Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key) for better security.

2\. Add Whonix's signing key.

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg add ~/patrick.asc
```

3\. Add Whonix's APT repository.

```
echo "deb https://deb.whonix.org buster main contrib non-free" | sudo tee /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `whonix-repository`.

```
sudo apt-get install whonix-repository
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions. (Replace `generic-package` with the actual name of this package `whonix-repository`.)

* **A)** [easy](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.whonix.org/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Donate ##

`whonix-repository` requires [donations](https://www.whonix.org/wiki/Donate) to stay alive!
