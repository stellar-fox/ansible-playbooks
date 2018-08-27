# Cygnus Deploy - Ansible Playbook

### Prerequisites: Ansible 2.6

    sudo dnf install ansible


### Playbook
This playbook builds the newest release of Cygnus and deploys the _build_ package to the server.



#### Run

Make sure that _config.json_ is present locally. Check _config.json.example_ for reference.
Ensure that _hosts_ file contains the correct webserver.

    ansible-playbook -i inventories/production/hosts inventories/production/site.yml --extra-vars "@config.json"
