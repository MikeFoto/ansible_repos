# repos Roles
Centos repository management

* Install a list of packages ( usually repos package )
* Ensure a list of repos are not present
* Ensure list of repos keys is imported
* Any number of repos with any configuration

# Usage

Define the Configuration hash some place . Check Examples at defaults/main.yml.ex

## Configuration Capabilities

```yaml
repos:
  key_list: []                          # list of repository keys to import
    # - "http://packages.elastic.co/GPG-KEY-elasticsearch"
  package_list: []                      # Optional list of packages to install .
  #                                       # optionally  with version (default to latest )
  # - { name: "bind-utils",        state: "latest" }
  names_to_remove:                      # Optional - List of repos definition to remove
    - repo2.repo
    - repo3.repo
  add:                                  # Also optional - list of repos to create
    - name: repo1
      content: |
       [custom_repo]
       name=Ansible repo build by ansible
       mirrorlist=http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=os&infra=$infra
       gpgcheck=1
       gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
```

# License

MIT

# Author Information

Created by Miguel Rodrigues
