=======================
About OpenStack-Ansible
=======================

OpenStack-Ansible (OSA) uses the `Ansible IT <https://www.ansible.com/how-ansible-works>`_
automation engine to deploy an OpenStack environment on Ubuntu Linux.
For isolation and ease of maintenance, you can install OpenStack components
into Linux containers (LXC).

This documentation is intended for deployers, and walks through an
OpenStack-Ansible installation for a test environment and production
environment.

Ansible
~~~~~~~

Ansible provides an automation platform to simplify system and application
deployment. Ansible manages systems using Secure Shell (SSH)
instead of unique protocols that require remote daemons or agents.

Ansible uses playbooks written in the YAML language for orchestration.
For more information, see `Ansible - Intro to
Playbooks <http://docs.ansible.com/playbooks_intro.html>`_.

In this guide, we refer to two types of hosts:

* `Deployment host` - The host running Ansible playbooks.
* `Target hosts` - The hosts where Ansible installs OpenStack services and
  infrastructure components.

Linux containers (LXC)
~~~~~~~~~~~~~~~~~~~~~~

Containers provide operating-system level virtualization by enhancing
the concept of ``chroot`` environments. These isolate resources and file
systems for a particular group of processes without the overhead and
complexity of virtual machines. They access the same kernel, devices,
and file systems on the underlying host and provide a thin operational
layer built around a set of rules.

The LXC project implements operating system level
virtualization on Linux using kernel namespaces and includes the
following features:

* Resource isolation including CPU, memory, block I/O, and network
  using ``cgroups``.
* Selective connectivity to physical and virtual network devices on the
  underlying physical host.
* Support for a variety of backing stores including LVM.
* Built on a foundation of stable Linux technologies with an active
  development and support community.


Installation workflow
~~~~~~~~~~~~~~~~~~~~~

This diagram shows the general workflow associated with an
OpenStack-Ansible installation.


.. figure:: figures/installation-workflow-overview.png
   :width: 100%

#. :ref:`deployment-host`
#. :ref:`target-hosts`
#. :ref:`configure`
#. :ref:`run-playbooks`
#. :ref:`verify-operation`
