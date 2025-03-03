EWC Ansible Role AIFS Single MSE
================================

Create a conda environment with AIFS Single MSE and associated software stack.

Requirements
------------

This ansible role depends on ewc-ansible-role-conda and needs to be applied on a GPU-powered instance.

Role Variables
--------------

 - `aifs_single_mse_env_wipe`: Boolean to decide whether to wipe the environment if exists prior to a reinstallation. Default: no
 - `aifs_single_mse_env_name`: Name of the environment containing the software stack. Default: aifs-single-mse
 - `aifs_single_mse_env_path`: Installation path for the environment. Default: "{{ conda_prefix }}/envs/{{ aifs_single_mse_env_name }}"
 - `aifs_single_mse_checkpoint`: URL to the model checkpoint. Default: https://huggingface.co/ecmwf/aifs-single-1.0/resolve/main/aifs-single-mse-1.0.ckpt
 - `aifs_single_mse_create_ipykernel`: Create the jupyter kernel for this environment. Default: yes
 - `conda_prefix`: Prefix where conda is installed. Default: `/opt/conda`
 - `conda_user`: User owning the conda installation. Default: `root`

Example Playbook
----------------

    - hosts: all
      roles:
         -  ewc-ansible-role-aifs-single-mse

License
-------

Apache 2.0.

Author Information
------------------

ECMWF for the European Weather Cloud