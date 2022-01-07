# Overview

This sample shows how an [Always Free](https://www.oracle.com/cloud/free/) public compute instance can be [launched](https://docs.us-phoenix-1.oraclecloud.com/Content/Compute/Tasks/launchinginstance.htm) and accessed through SSH, using OCI ansible cloud modules.
- More detail in my [blog post](https://brokedba.blogspot.com/2020/07/launch-oci-instance-with-ansible-in-10.html).
![Topology](https://brokedba.files.wordpress.com/2020/08/image-4.png?w=853)
The sample 
- generates a temporary host-specific SSH key-pair
- specifies the public key from that key-pair to connect to the instance during instance launch and 
- demonstrates how the newly launched instance can be connected to using SSH.
- config_profile_name: "{{config_profile}}" has been added so you use a specific profile listed in your oci config file(~.oci/config.cfg)
- check_network and check_shapes are quick playbooks(get facts) to run in case you would like to validate the corectness of your setup. 

# Instructions

This can only work if you install oci-ansible  modules from ansible-galaxy as I adapted the playbook to use roles instead of the original module calls available in the oracle official GitHub Repo.

```
-------- automatic galaxy install -------------------------------------
The default path for the roles is the first writable directory configured via DEFAULT_ROLES_PATH: ~/.ansible/roles:/usr/share/ansible/roles:/etc/ansible/roles
$ ansible-galaxy install --roles-path=/etc/ansible/roles   (or -p)
$ ansible-galaxy list
- oracle.oci_ansible_modules, v1.18.0
PATH : ~/.ansible/roles/oracle.oci_ansible_modules
```

To run the sample, after ensuring that you have the pre-requisites for OCI ansible cloud modules, please provide values (that are specific to your tenancy) for the following variables in the file `a_env_vars` and source it:
- SAMPLE_COMPARTMENT_OCID


Once all set you can just call the sample playbook
```
# ansible-playbook sample.yaml
```



