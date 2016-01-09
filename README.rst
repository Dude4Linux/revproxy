revproxy - NGINX Reverse Proxy
==============================

`revproxy`_ is a reverse web proxy based on NGINX and Dnsmasq. It is
designed to allow multiple web domains to share a single public ip
address. The web domains can be hosted by virtual hosts on an internal
server, on separate virtual machines for secure isolation, or on
multiple physical machines.

This appliance includes all the standard features in `TurnKey Core`_, and on
top of that:

- Easily expose web services:

    - `nginx-proxy`_: Expose web services to the Internet by creating
      an nginx site configuration to proxy all web requests (ports 80, 443)
      destined for a specific domain to the container on the
      corresponding ports.
    - `turnkey-make-ssl-cert`_: Easily create self-signed certificates
      and certificate requests (CSR) for your custom domains.
    - `iptables-nat`_: Expose a non-web (e.g. SSH) service to the
      Internet by configuring iptables on the host to forward the
      traffic it receives on port X to the container on port Y.

- revproxy appliance configurations:

    - Preconfigured Dnsmasq providing DHCP and DNS services.
    - SSL offloading, encryption, and certificate management with NGINX
    - Optionally encrypt traffic to upstream servers
    - Memcached for improved cache performance
    - Fail2ban configured to block unwanted traffic and DDOS attacks
    - Accepts Fail2ban requests from upstream servers
    - Includes TurnKey web control panel (convenience).

See the `Usage documentation`_ for further details.

Credentials *(passwords set at first boot)*
-------------------------------------------

-  Webmin, SSH: username **root**

.. _TurnKey Core: https://www.turnkeylinux.org/core
.. _revproxy: https://github.com/turnkeylinux-apps/revproxy
.. _nginx-proxy: https://github.com/turnkeylinux-apps/revproxy/blob/master/overlay/usr/local/bin/nginx-proxy
.. _turnkey-make-ssl-cert: https://github.com/turnkeylinux-apps/revproxy/blob/master/overlay/usr/bin/turnkey-make-ssl-cert
.. _iptables-nat: https://github.com/turnkeylinux-apps/revprox/blob/master/overlay/usr/local/bin/iptables-nat
.. _Usage documentation: https://github.com/turnkeylinux-apps/revprox/tree/master/docs

