# ToDo

Plain ToDo file for whiletruedoio.general.

## Release v1.0.0

- [ ] update playbooks
  - [ ] update role

- [ ] minimal server playbook
  - [x] bash role
  - [ ] chrony role (client only)
  - [x] dnf role
    - [ ] add dnf automatic
  - [x] firewalld role
  - [x] misc role
  - [x] selinux role
  - [x] sshd role
  - [ ] sudo role
  - [x] user role

- [ ] base server playbook
  - [ ] minimal server playbook
  - [ ] cockpit role
  - [ ] kdump role
  - [ ] pcp role
  - [x] thermald role
  - [ ] tuned role

- [ ] Update user documentation

## Release v2.0.0

- [ ] kvm server playbook
  - [ ] base server playbook
  - [ ] cockpit role + cockpit machines
  - [ ] kvm role

- [ ] podman server playbook
  - [ ] base server playbook
  - [ ] cockpit role + cockpit podman
  - [ ] podman role

- [ ] ansible server playbook
  - [ ] minimal server playbook
  - [ ] ansible role
  - [ ] git role (client only)

- [ ] httpd server playbook
  - [ ] minimal server playbook
  - [ ] httpd role

- [ ] mariadb server playbook
  - [ ] minimal server playbook
  - [ ] mariadb role

## Release v3.0.0

- [ ] docker server playbook
  - [ ] minimal server playbook
  - [ ] docker role

- [ ] lxc server playbook
  - [ ] minimal server playbook
  - [ ] lxc role

- [ ] nfs server playbook
  - [ ] minimal server playbook
  - [ ] nfs role (nfsv3/4)

- [ ] k3s single server playbook
  - [ ] minimal server playbook
  - [ ] k3s role (single server deployment)

- [ ] git server role
  - [ ] minimal server playbook
  - [ ] git role (server + gitweb)

- [ ] time server playbook
  - [ ] minimal server playbook
  - [ ] chrony role (server)

## Release vX.0.0

- [ ] k3s cluster playbook
  - [ ] minimal server playbook
  - [ ] k3s role (1-3 masters + 0-n workers)

- [ ] postgresql server playbook
  - [ ] minimal server playbook
  - [ ] postgresql role

- [ ] haproxy server playbook
  - [ ] minimal server playbook
  - [ ] haproxy role

- [ ] openvpn server playbook
  - [ ] minimal server playbook
  - [ ] openvpn role

- [ ] pki server playbook
  - [ ] minimal server playbook
  - [ ] easyrsa role

- [ ] gitlab runner playbook
  - [ ] minimal server playbook
  - [ ] docker role
  - [ ] git role (client only)
  - [ ] gitlab runner role

- [ ] jenkins agent playbook
  - [ ] minimal server playbook
  - [ ] docker role
  - [ ] git role (client only)
  - [ ] java role
  - [ ] jenkins agent role

- [ ] lamp server playbook
  - [ ] minimal server playbook
  - [ ] httpd role
    - mod_ssl
    - mod_security
    - mod_md
    - mod_http2
  - [ ] mariadb role
    - including some hardening
  - [ ] php role
    - common php modules (ex. nextcloud/wordpress list)
