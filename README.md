[![Build Status](https://travis-ci.org/jnakatsui/ansible-role-s3cmd.svg?branch=master)](https://travis-ci.org/jnakatsui/ansible-role-s3cmd)

s3cmd
=====
Installs s3cmd

Requirements
------------
None to install - but a Amazon S3 account to use

http://s3tools.org/s3cmd

Added pip install and OS supprt for Debian / Redhat


Role Variables
--------------
become_user: The user to run the role as

s3cmd_pkgs: Required python dependencies
  - python-setuptools
  - python-dateutil
  - python-magic

aws_access_key: supply your access key in (vaulted) host_vars / group_vars
aws_secret_key: supply your secret key in (vaulted) host_vars / group_vars

s3cmd_repo: "https://github.com/s3tools/s3cmd" - the repo to install from
s3cmd_dest: "/root/s3cmd" the default install location
s3cmd_version: "v1.5.2" - the version to install
s3cmd_cfg_path: "/root/.s3cfg" - the path of the config file


Note that on Centos I changed thegroup ownership of /ur/lib/python2.6/site-packages to ansible admin group
Otherwise it only runs for root


Dependencies
------------
None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ansible-role-s3cmd }

License
-------
MIT

Credits:
--------
Forked from jnakatsui
