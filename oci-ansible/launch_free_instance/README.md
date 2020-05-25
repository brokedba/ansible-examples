# Overview

This sample shows how an [Always Free](https://www.oracle.com/cloud/free/) public compute instance can be [launched](https://docs.us-phoenix-1.oraclecloud.com/Content/Compute/Tasks/launchinginstance.htm) and [accessed](https://docs.us-phoenix-1.oraclecloud.com/Content/Compute/Tasks/accessinginstance.htm) from the internet using SSH, through OCI ansible cloud modules.

The sample 
- generates a temporary host-specific SSH key-pair
- specifies the public key from that key-pair to connect to the instance during instance launch and 
- demonstrates how the newly launched instance can be connected to using SSH.
- config_profile_name: "{{config_profile}}" has been added so you use a specific profile listed in your oci config file(~.oci/config.cfg)
- check_network and check_shapes are quick playbooks(get facts) to run in case you would like to validate the corectness of your setup. 

# Instructions

To run the sample, after ensuring that you have the pre-requisites for OCI ansible cloud modules, please provide values (that are specific to your tenancy) for the following variables in the file `a_env_vars` and source it:
- SAMPLE_COMPARTMENT_OCID
