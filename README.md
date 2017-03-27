Role Name
=========

Installs acme.sh and issues certificates through Let's Encrypt.

Requirements
------------

Openssl, Git and SH / Bash. Will work with FreeBSD 11 and base. (+git)

Role Variables
--------------

```
acme_le_acme_download_folder: "~/checkouts/"
```  

Where git will check out acme.sh

```
acme_le_acme_home_folder: "~/.acme.sh"
```  

Where acme.sh is installed

```
acme_le_ssl_folder: "~/ssl/"
```

Where the certificates are stored

```
acme_le_standalone_port: 8080
```

Which port to listen on in standalone mode (>1024 does not require root)  

```
acme_le_user: acme
```

The user that will be created for running acme.sh

```
acme_le_webroot
```

Whether to use webroot or standalone

Dependencies
------------

None, though a jail can be helpful

Example Playbook
----------------


		- hosts: acme-le
  	  	  vars:
  	  	    vhosts:
  	  	    - server_name: "example.com"
           acme_le_vhosts: "{{ vhosts }}"
           acme_le_webroot: no
  		  roles:
         - bvansomeren.acme-le

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
