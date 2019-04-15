# vagrant-centos-ansible

ansible and molecule test vagrantfile

Windows 10 Pro Ver.1803 (Hyper-V enabled) + Vagrant 2.2.4

```console
$ vagrant up
Bringing machine 'default' up with 'hyperv' provider...
==> default: Verifying Hyper-V is enabled...
==> default: Verifying Hyper-V is accessible...
==> default: Importing a Hyper-V instance
    default: Creating and registering the VM...
    default: Successfully imported VM
    default: Please choose a switch to attach to your Hyper-V instance.
    default: If none of these are appropriate, please open the Hyper-V manager
    default: to create a new virtual switch.
    default:
    default: 1) 既定のスイッチ
    default: 2) nat
    default:
    default: What switch would you like to use? 1
    default: Configuring the VM...
==> default: Starting the machine...
==> default: Waiting for the machine to report its IP address...
    default: Timeout: 120 seconds
    default: IP: 172.19.119.229
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 172.19.119.229:22
    default: SSH username: vagrant
    default: SSH auth method: private key
    default:
    default: Vagrant insecure key detected. Vagrant will automatically replace
    default: this with a newly generated keypair for better security.
    default:
    default: Inserting generated public key within guest...
    default: Removing insecure key from the guest if it's present...
    default: Key inserted! Disconnecting and reconnecting using new SSH key...
==> default: Machine booted and ready!
==> default: Rsyncing folder: /cygdrive/c/Users/user/vagrant-centos-ansible/ => /vagrant
==> default: Running provisioner: ansible_local...
    default: Installing Ansible...
Vagrant has automatically selected the compatibility mode '2.0'
according to the Ansible version installed (2.7.9).

Alternatively, the compatibility mode can be specified in your Vagrantfile:
https://www.vagrantup.com/docs/provisioning/ansible_common.html#compatibility_mode
    default: Running ansible-playbook...

PLAY [provisioning] ************************************************************

TASK [Gathering Facts] *********************************************************
ok: [default]

TASK [yum update] **************************************************************
changed: [default]

TASK [install requires] ********************************************************
changed: [default]

TASK [install molecule] ********************************************************
changed: [default]

PLAY RECAP *********************************************************************
default                    : ok=4    changed=3    unreachable=0    failed=0
```

## main.ymlを変更した場合の反映方法

```console
$ vagrant reload --provision
==> default: Attempting graceful shutdown of VM...
    default: Configuring the VM...
==> default: Starting the machine...
==> default: Waiting for the machine to report its IP address...
    default: Timeout: 120 seconds
    default: IP: 172.19.119.229
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 172.19.119.229:22
    default: SSH username: vagrant
    default: SSH auth method: private key
==> default: Machine booted and ready!
==> default: Rsyncing folder: /cygdrive/c/Users/user/vagrant-centos-ansible/ => /vagrant
==> default: Running provisioner: ansible_local...
Vagrant has automatically selected the compatibility mode '2.0'
according to the Ansible version installed (2.7.9).

Alternatively, the compatibility mode can be specified in your Vagrantfile:
https://www.vagrantup.com/docs/provisioning/ansible_common.html#compatibility_mode
    default: Running ansible-playbook...

PLAY [provisioning] ************************************************************

TASK [Gathering Facts] *********************************************************
ok: [default]

TASK [yum update] **************************************************************
ok: [default]

TASK [install requires] ********************************************************
ok: [default]

TASK [install molecule] ********************************************************
ok: [default]

PLAY RECAP *********************************************************************
default                    : ok=4    changed=0    unreachable=0    failed=0

```
