# API Docs Deploy - Ansible Playbook

### Prerequisites: Ansible 2.6

    sudo dnf install ansible

#### Creating a release on Github (Prerequisite)

The newer release must be created first on Github with
a tag bearing semantic versioning scheme
(ie: v.X.Y.ZZ) To create a release on Github, tag the
master branch with signed annotated tag.

    git tag -s v.X.Y.ZZ
    git push origin --tags

Update **`tag`** and **`tag_2_less`** in `config.json`
file to the current tag and tag two releases less than
current in order to rotate release stack on production
server.


### Playbook
This playbook builds the release that is specified in
`config.json`'s **`tag`** property and deploys the
_build_ package to the server.



#### Run

Make sure that _config.json_ is present locally. Check _config.json.example_
for reference.
Ensure that _hosts_ file contains the correct webserver. Execute the following
from within this directory (_api.docs.deploy_)

    ansible-playbook -i inventories/production/hosts inventories/production/site.yml --extra-vars "@config.json"
