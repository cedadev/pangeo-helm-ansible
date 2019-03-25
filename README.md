# Ansible role to install Pangeo helm chart

This role deploys a Pangeo help chart on an existing Kubernetes cluster. It is
assumed that helm client is available on the host and a tiller pod is available
to the client.

To test:

    ansible-playbook -i tests/inventory.ini tests/main.yml -e pangeo_state=present

To delete the chart:

    ansible-playbook -i tests/inventory.ini tests/main.yml -e pangeo_state=present

The configurable parameters are:

    pangeo_state: present
    pangeo_hosts: [""]
    pangeo_password:
    pangeo_users: []
    pangeo_admin_users: []
    pangeo_namespace: pangeohub
    pangeo_storage_class: standard
    pangeo_storage_capacity: 10G
    pangeo_image_name: pangeo/pangeo-notebook
    pangeo_image_tag: 2019.03.12
    pangeo_version: 19.03.05

To build custom notebook, refer to this repo: https://github.com/pangeo-data/pangeo-stacks/.

To lookup more up to date image tags, refer to this repo: https://hub.docker.com/r/pangeo/pangeo-notebook/tags/.

To lookup up to date Pangeo charts, refer to this page: https://pangeo-data.github.io/helm-chart/.
