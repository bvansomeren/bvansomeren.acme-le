bvansomeren.acme
================

Installs acme.sh and issues certificates through Let's Encrypt.

Requirements
------------

Will work with FreeBSD 11 and base.

Role Variables
--------------

```
acme_download_folder: "~/checkouts/"
```  

Where git will check out acme.sh

```
acme_acme_home_folder: "~/.acme.sh"
```  

Where acme.sh is installed

```
acme_ssl_folder: "~/ssl/"
```

Where the certificates are stored

```
acme_standalone_port: 8080
```

Which port to listen on in standalone mode (>1024 does not require root)  


```
acme_webroot
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
           acme_vhosts: "{{ vhosts }}"
           acme_webroot: no
  		  roles:
         - bvansomeren.acme

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
