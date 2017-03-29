# &#128267; CyberPower role for Ansible

[![Build Status](https://img.shields.io/travis/paulborza/cyberpower-ansible-role/master.svg)](https://travis-ci.org/paulborza/cyberpower-ansible-role)
[![Ansible Role](https://img.shields.io/ansible/role/16551.svg)](https://galaxy.ansible.com/paulborza/cyberpower/)

## Supported OS

- Ubuntu
  - Ubuntu 14.04 LTS (Trusty Tahr)
  - Ubuntu 16.04 LTS (Xenial Xerus)
  - Ubuntu 16.10 (Yakkety Yak)
- Debian
  - Debian 8.0 LTS (Jessie)

## Usage

First, download the CyberPower role locally.

```bash
ansible-galaxy install --force paulborza.cyberpower
```

Second, create a file named `example-playbook.yml`. Use the following YAML file as example.

```
- hosts: all
  roles:
    - paulborza.cyberpower

  tasks:
    - name: print a happy message
      command: echo "Computer now listens to CyberPower UPS shutdown instructions. Yay!"
```

Third, create another file named `hosts` by running `echo localhost > hosts`. Feel free to update the hosts file to match your infrastructure configuration.

Finally, execute the playbook against the servers listed in the `hosts` file.

```bash
ansible-playbook ./example-playbook.yml -i ./hosts
```

## Loss of power

If there's a loss of power, the computer will be shutdown automatically.
To test the CyberPower UPS, fully charge it first, and then unplug it; it'll start beeping from time to time. You can also check the status of the UPS with the following command.

```bash
pwrstat -status
```

```
The UPS information shows as following:

	Properties:
		Model Name................... CP1500AVRLCDa
		Firmware Number.............. CTHFU2000557
		Rating Voltage............... 120 V
		Rating Power................. 900 Watt(1500 VA)

	Current UPS status:
		State........................ Power Failure
		Power Supply by.............. Battery Power
		Utility Voltage.............. 0 V
		Output Voltage............... 120 V
		Battery Capacity............. 100 %
		Remaining Runtime............ 34 min.
		Load......................... 198 Watt(22 %)
		Line Interaction............. None
		Test Result.................. Unknown
		Last Power Event............. Blackout at 2017/03/26 11:40:07
```

## Contributing

Got a new OS you'd like to see supported by this role?
Please go ahead and [create a work item](https://github.com/paulborza/cyberpower-ansible-role/issues/new) for me; or better yet, send a pull request and I'll be sure to take a look at it within 24 hours. Thanks!
