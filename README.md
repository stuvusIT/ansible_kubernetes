# ansible_kubernetes

This role installs [Kubernetes](https://github.com/kubernetes/kubernetes) on Debian.
That is, the packages `kubeadm`, `kubelet` and `kubectl` will be installed.


## Requirements

[Debian](https://www.debian.org/).
Maybe this role also works on other apt based systems.


## Role Variables

| Name                 | Required | Description                                         |
| :------------------- | :------- | :-------------------------------------------------- |
| `kubernetes_version` | yes      | See [Version Specification](#version-specification) |


## Version Specification

The variable `kubernetes_version` must contain the major and minor version of the Kubernetes version
to install.
The newest available patch of that version will be installed.
Example:

```yml
kubernetes_version: "1.19"
```


## Example Playbook

The following example playbook assumes that you cloned this role to `roles/kubernetes`
(i.e. the name of the role is `kubernetes` instead of `ansible_kubernetes`).

```yml
- hosts: kube01
  roles:
    - role: kubernetes
      kubernetes_version: "1.19"
```


## License

This work is licensed under the [MIT License](./LICENSE).


## Author Information

- [Sebastian Hasler (haslersn)](https://github.com/haslersn) _sebastian.hasler at stuvus.uni-stuttgart.de_
