Ansible Role - Mac Setup: Changelog
=====================================
A list of all the changes made to this repo, and the role it contains

Version 1.2.0
-------------

1. Monterey/Apple Silicon initial support
2. Deploy Rosetta 2
3. Adding the following taps/brews/casks
   1. `poetry`
4. Removing the following taps/brews/casks
   1. `parera10/csshx`
   2. `docker-machine`
   3. `docker-machine-driver-vmware`
   4. `exiftool`
   5. `minikube`
   6. `openssh`
   7. `profilecreator`
   8. `wireshark`
5. `saml2aws-duo` is now just `saml2aws as it's officially supporting Duo on JumpCloud
6. Moving the following brews to deploy only on Intel (for now)
   1. `dc3dd`
   2. `vfuse`
7. Moving the following casks to deploy only on Intel (for now)
   1. `vmware-fusion`
   2. `homebrew/cask-drivers/yubico-yubikey-manager`
   3. `homebrew/cask-drivers/yubico-yubikey-personalization-gui`
   4. `vagrant-vmware-utility`
   5. `vagrant`
   6. `virtualbox`

Version 1.1.5
-------------

1. Removing `osxfuse` package from Homebrew tasks
2. `docker` formula removed from Homebrew because `docker` cask is all we need

Version 1.1.4
-------------

1. Adding `fzf`
   1. Added as a brew
   2. Run `yes | /usr/local/opt/fzf/install` to configure fzf 
2. Remove the `sshfs` brew because it's deprecated

Version 1.1.3
-------------

1. Updated .gitconfig template to use `main` as the default branch name for new repos

Version 1.1.2
-------------

1. Updated Homebrew code now that casks are part of the main brew command
2. Added the following brews
    1. ripgrep
3. Added a rebase config setting to .gitconfig

Version 1.1.1
-------------

1. Fixed things required for Big Sur support (**Intel only**)
2. Removed the following casks:
    1. aerial
    2. openra
    3. google-drive-file-stream
3. Added the following casks:
    1. discord
    2. handbrake
    3. suspicious-package
    4. vlc
    5. wireshark
    6. yubico-yubikey-manager
    7. yubico-yubikey-personalization-gui
4. Added the following brews
    1. readline
    2. zlib
    3. xz
5. Fixed licensing logic
6. Corrected some minor typos
7. Removed spotlight settings
8. Updated Menu Bar preferences to Big Sur keys
9. Disable Ad Personalization
10. Fixed Python 3.8.0 installation method (This can hopefully be made less complicated later)
11. Removed showing Fast User Switcher
12. Disabled mouse and trackpad tasks for now as they don't work

Version 1.1.0
-------------

1. CommandQ can now be optionally licensed
2. The Ruby environment is preconfigured as 2.7.0
3. The Python environment is preconfigured as 3.8.0
4. Fixed platform version in role metadata
5. Fixed xattr task in Homebrew

Version 1.0.0
-------------

1. Initial Release of repository

Role Changes:

1. Initial release

Return to [README](README.md)
