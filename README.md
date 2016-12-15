# ovirt-hooks

## 99_disable_x2apic
This script is used to disable x2apic on the cpu.
Solaris servers running in ovirt have no network connectivity when x2apic is enabled.

### Installation
* Install the script under /usr/libexec/vdsm/hooks/before_vm_start
* Run following commands on the ovirt-engine host
```
engine-config -s 'UserDefinedVMProperties=disable_x2apic=^(true|false)$' --cver=4.0
service ovirt-engine restart
```

### Usage
In the VM configuration window, open the custom properties tab and add disable_x2apic=true
