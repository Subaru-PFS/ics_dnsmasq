Overall
======

Refer documentation (`SSN-00028 in ics_doc repository <https://github.com/Subaru-PFS/ics_doc/tree/master/SSN-00028>`_) 
for organization of directories and files. 
Pushing to master is allowed, but it is recommended to follow the normal 
procedure (ticket and PR) to push items into the site-wide (macs/ and 
dnsmasq.conf) ad the production (hosts-subaru/ and dnsmasq-site.subaru), 
to make decisions visible with reasons and discussions/reviews logged. 
For installation at each site, 
`Ansible role <https://github.com/Subaru-PFS/ics_ansible/tree/master/roles/dnsmasq>`_ 
is provided, and it is recommended to configure using ansible if possible. 

Target
======

This dnsmasq configuration is intended to:

- Assign static hostname to IP address bindings. 
- Manage hostname to MAC address bindings, so that hardware can be
  pinned down and used for DHCP.
- Provide local DNS resolution for the PFS hosts. The actor softwre
  uses names.
- Support PXE booting: the DHCP options and the tftp server. The BEE
  needs this, as might other systems.

Notes
=====

- If you want to resolv using configurations in here on an host which hosts 
  dnsmasq, you need to add 'server=' line(s) and set '127.0.0.1' in 
  '/etc/resolv.conf' (or a configuration file your server read). 
- To add/remove configuration in dnsmasq.conf or dnsmasq-site.\*, file a ticket 
  and get reviews. 

