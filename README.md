Ansible Role - Mac Setup
==========================
This repo contains an Ansible role that configures Matthew Ahrenstein's personal preferences and settings on a new out-of-the-box Mac.  
This drastically speeds up how long it takes to setup a new Mac for me.

Apple Silicon
-------------
Right now this Ansible role is tested against Sonoma on **Apple Silicon** Macs only.

Monterey and MDM
----------------
This repository is tested against machines enrolled in MDM via DEP with a configuration profile that allowlists system extensions from the
following vendor IDs:

| Vendor Name  | Team ID         | KEXT IDs                               |
|--------------|-----------------|----------------------------------------|
| VMware       | EG7KH642X6      | (ALL)                                  |
| Rogue Amoeba | 7266XEXAPM      | /Library/Audio/Plug-Ins/HAL/ACE.driver |

If these are not allowlisted ahead of running this role, you may have to approve system extensions as prompts come up. This is due to some of the Homebrew casks that get installed.  
Additionally, on Apple Silicon computers you must [enable Reduced Security ahead of running this to allow the Rogue Amoeba apps to install](https://rogueamoeba.com/support/knowledgebase/?showArticle=ACE-StepByStep).

Requirements
------------
To configure a machine you must have the following:

1. macOS Sequoia (15.0) or later (This may work on earlier versions, but only the latest is tested)
2. The account you're using must be an Admin
3. Internet access
4. [Homebrew](https://brew.sh/) pre-installed
5. [Ansible](http://www.ansible.com/) pre-installed via Homebrew

Limitations
------------

1. This role is not meant to be run against remote machines
2. This role will prompt for the logged-in user's password in order to use sudo for the Homebrew steps
3. **Logging out after the role completes is recommended as some settings don't apply until a new login occurs**

Variables
---------
There are a few variables defined in this role

The following variables should be changed as they default to my identity:

1. `full_name` - Your first and last name
2. `email` - Your email address
3. `gpg_short_id` - Your GPG key's short ID

Changing the following variables is less required but are still very personal in taste:

1. `homebrew_taps` - Change the default taps installed
2. `homebrew_packages` - Change the default brews that are installed
3. `homebrew_casks` - Change the default casks that are installed
4. `licenses` - Change this to `true` to run the licenses tasks (You will also need to populate the below licensing variables)

Licensing variables:

1. `loopback_license` and `loopback_name` - Licensing info for Rogue Amoeba's [Loopback](https://rogueamoeba.com/loopback/)
2. `audiohijack_license` and `audiohijack_name` - Licensing info for Rogue Amoeba's [Audio Hijack](https://rogueamoeba.com/audiohijack/)
3. `soundsource_license` and `soundsource_name` - Licensing info for Rogue Amoeba's [SoundSource](https://rogueamoeba.com/soundsource/)
4. `fission_license` and `fission_name` -  - Licensing info for Rogue Amoeba's [Fission](https://rogueamoeba.com/fission/)
5. `farrago_license` and `farrago_name` - Licensing info for Rogue Amoeba's [Farrago](https://rogueamoeba.com/farrago/)
6. `viscosity_license` - Licensing info for [Viscosity VPN Client](https://sparklabs.com/viscosity/)
7. `commandq_license` - Licensing info for [CommandQ](https://commandqapp.com/) (The format is `email,license key` encoded in base64 with no new line) 

Running this role locally
-------------------------
To run this role against the local machine simply run `ansible-playbook playbook-local.yml -i local.inventory`  
To go from zero (no Homebrew or Ansible) to 100% you can optionally run something like [devops-mac](https://github.com/route1337/devops-mac) which uses this role.

Testing
-------
This role is manually tested against VMs.  
[TESTING.md](TESTING.md) contains details and instructions for testing. 
