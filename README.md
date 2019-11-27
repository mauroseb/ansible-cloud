# Ansible OpenStack Smoke Test

## Usage

1. Clone in bastion host

2. Edit ssh.cfg and osp_inventory_hosts (alternatively group_vars/all also points to the stack name ```overcloud``` in this csae)

3. Edit your /etc/openstack/clouds.yaml
~~~
clouds:
 undercloud:
    auth:
        auth_url: https://undercloud-keystone.local:13000/
        password: XXX
        project_domain_name: Default
        project_name: admin
        user_domain_name: Default
        username: admin
    identity_api_version: '3'
 overcloud:
    auth:
        auth_url: http://overcloud-keystone.local:5000/v3
        password: XXX
        project_domain_name: Default
        project_name: admin
        user_domain_name: Default
        username: admin
    identity_api_version: '3'
~~~

4. Run

    $ export OS_CLOUD=overcloud
    $ ansible-playbook site.yml
