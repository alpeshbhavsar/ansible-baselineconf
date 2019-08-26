Baselineconf
=========

This ansible role is written to apply base configuration on operating system once fresh OS is installed. I mostly follow few steps once OS is ready, so want to leverage automated installation/configuration through Ansible. This playbook should work for both CentOS & Ubuntu. It does following.
   - Install few default packages like vim, unzip, wget
   - Disable SELinux
   - Disable UseDNS and GSSAPI Auth options for ssh connections
   - Set Hostname
   - Stop and Disable firewall

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

- hostname - This variable has been defined in default/main.yaml file. When you want to set hostname to something else other than localhost, you can specify hostname by -e "hostname=samplehostname" in ansible-playbook command.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
<pre>
ansible-playbook init.yaml -e "hostname=samplehostname"
init.yaml
    - name: Setup environment
      hosts: all
      become: yes
      roles:
        - role: alpeshbhavsar.ansible_baselineconf
</pre>

License
-------

BSD

Author Information
------------------

Written by Alpesh
