Ansible Role: Kubernetes Join Nodes
=========

Joins worker nodes to an existing Kubernetes cluster.

Requirements
------------

Kubernetes binaries should already be installed (kubelet, kubeadm, kubectl).

Role Variables
--------------

None

Dependencies
------------

This playbook depends on the `ansible-role-kubernetes-prep` role having been executed on the hosts prior to running
and that an existing Kubernetes cluster is available.

Example Playbook
----------------

    # ===========================================================================
    # Join nodes to Kubernetes cluster
    # ===========================================================================
    - name: Join Kubernetes nodes to cluster
    hosts: k8s_nodes
    tags: play_k8s_nodes

    vars_files:
        # Ansible vault with all required passwords
        - "/home/apatt/github/demopod-ansible/credentials.yml"

    roles:
        - ansible-role-kubernetes-join-nodes

License
-------

MIT

Author Information
------------------

Aaron Patten
aaronpatten@gmail.com
