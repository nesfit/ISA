# Vagrant for ISA projects
* [Vagrant documentation](https://www.vagrantup.com/docs/)

## First run
```bash
$ git clone https://github.com/nesfit/ISA.git
$ cd ISA/projects/vagrant
$ vagrant up [--provider virtualbox|hyperv|vmware_desktop,libvirt]
$ vagrant ssh
```

## Usage
* *Suspend* virtual machine (saves current state without shutting VM down) `$ vagrant suspend`
* *Resume* virtual machine (if VM was previously suspended) `$ vagrant resume`
* *Start* virtual machine (applies Vagrantfile configuration but keeps data) `$ vagrant reload`
* *Stop* virtual machine `$ vagrant halt`
* *Delete* virtual machine `$ vagrant destroy`
