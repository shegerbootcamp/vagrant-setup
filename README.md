# Building a VM with Vagrant

This guide provides instructions to set up and manage VMs using Vagrant, specifically for Kubernetes certification. 

## Prerequisites

- Ensure you have Vagrant installed. You can download it from [here](https://www.vagrantup.com/downloads).
- Ensure you have VMware for ubuntu installed or VMware Fusion if you are using a Mac.
- Ensure you have the `bento/ubuntu-22.04` Vagrant box for ARM architecture if you are using a Mac.

## Cloning the Repository

To test the setup, clone the Kubernetes certification repo which contains the Vagrantfile to deploy three VMs.

```bash
git clone https://github.com/techiescamp/kubernetes-certification-guide.git
```

Navigate to the Mac Silicon folder where the Vagrantfile is located:

```bash
cd kubernetes-certification-guide/lab-setup/mac-silicon
```

The folder contains a `Vagrantfile` with the `bento/ubuntu-22.04` Vagrant box for ARM architecture, which deploys three VMs. You can modify the VM details in the `settings.yaml` file present in the folder.

## Bringing Up the VMs

Use the following command to bring up the VMs. **Important Note:** Ensure you use `sudo` with the command. Without `sudo`, it won't work.

```bash
sudo vagrant up
```

This should bring up three VMs.

## Using the VM

To login to a specific VM, use the node name with ssh. First, get the node names by executing:

```bash
sudo vagrant status
```

You should see output similar to:

```
Current machine states:

controlplane              running (vmware)
node01                    running (vmware)
node02                    running (vmware)
```

Use the machine names to SSH into a VM. For example:

```bash
sudo vagrant ssh controlplane
```

## Managing the VMs

To stop the VMs, run:

```bash
sudo vagrant halt
```

To bring the VMs up again, run:

```bash
sudo vagrant up
```

## Modifying VM Settings

You can modify the VM settings by editing the `settings.yaml` file present in the folder. Make the necessary changes and then bring up the VMs again using `sudo vagrant up`.

---

This README provides an overview and instructions for setting up and managing VMs using Vagrant. Feel free to customize it further based on your specific requirements.
