![Build Status](https://github.com/annacprice/ansible.bactocap/workflows/ansible-ci/badge.svg)
# ansible.bactocap

This playbook installs the following
* [Nextflow](https://www.nextflow.io) 22.10.4
* [Docker](https://www.docker.com) 5:20.10.21\~3-0~ubuntu-focal
* [Go](https://go.dev) 1.19.3
* [Singularity](https://sylabs.io/singularity) v3.10.4
* [Miniconda](https://docs.conda.io/en/latest/miniconda.html) 4.12.0

It is designed to run on a clean Ubuntu 20.04 server (i.e. a server on which nextflow etc. have not yet been installed).

This repo also contains a GitHub Actions workflow which tests the playbook.

## Install instructions
Install ansible
```
sudo apt update
sudo apt install ansible
```

Clone the repo
```
git clone https://github.com/annacprice/ansible.bactocap.git
```
Run the playbook
```
cd ansible.bactocap
ansible-playbook playbook.yml
```

## Updating software versions
The versions for the installed software are found in `ansible.bactocap/roles/bactocap/defaults/main.yml`. 
These can be updated. When updates are made to the playbook, a new GitHub Actions run is triggered.

To check for the latest versions of Nextflow look [here](https://github.com/nextflow-io/nextflow/releases)

Versions of Singularity can be found [here](https://github.com/sylabs/singularity/releases). 
The release notes should suggest which version of Go to use.
Note that Singularity is end of life and will be replaced with [Apptainer](https://github.com/apptainer/apptainer)

A list of the latest versions of Docker can be found [here](https://docs.docker.com/engine/release-notes/). 
To update the version in the ansible you'll have to use the following format `5:VERSION-NO-HERE~3-0~ubuntu-focal`
