# Ansible Role - ssl-certs

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

## Input and Variables

```yaml
flags:
  force: set to true to force any of the previous actions
  client_config: set to true to ensure the proper SSL settings for generating a client certificate
  create_csr: set to true to generate a new CSR on a remote machine
  pull_csr: set to true to copy CSR local
  deploy: set to true to deploy certificates
  create_ssc: set to true to create a Self Signed Certificate
  dh_param: set to true to generate a dhparam file

cert_config:
  country: Country
  locality: Locality
  state: State
  organization: Organization
  ou: Organizational Unit
  cn: Common name, usually fqdn
  dc: Domain Component, if any
  email: Email
  subject: Subject
```

## Examples

### Example to generate a Certificate Signing Request

```yaml
- hosts: all
  gather_facts: inventory_hostname != 'localhost'
  vars:
    flags:
      - client_config
      - force
      - create_csr
  roles:
    - { role: nholuong.ssl-certs }
```

## Example to move a certificate into place

```yaml
- hosts: all
  gather_facts: inventory_hostname != 'localhost'
  vars:
    flags:
      - deploy
  roles:
    - nholuong.ssl-certs
```

## Linting

```bash
yamllint -c yamllint.yaml .
ansible-lint .
```

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟