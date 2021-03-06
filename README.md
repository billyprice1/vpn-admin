# VPN-Admin

VPN-Admin is a collection of CLI utilities to manage an OpenVPN system running on the Raspberry Pi.  The OpenVPN system these script are design to manage have some limitation and don't take into account all the best practices for managing an OpenVPN system.  The first is that all keys and certificates are generated by one person.  Secondly the keys and certificates are generated on the same system that runs the OpenVPN server.  Therefore these scripts should only be used on a small OpenVPN system where there is a high level of trust between users, such as a family or small technical group. 

## Getting Started

Full details on how to setup and manage an OpenVPN system on the Raspberry can be found at [http://www.mdwight.com/OpenVPN](http://www.mdwight.com/OpenVPN).

## Prerequisites

The scripts have been tested on Raspberry Pi (1,2 and 3) model B boards running Raspbian Stretch Lite.   The scripts were tested against OpenVPN v2.4 and easy-RSA v3.

## Examples

The following shows the various CLI utilities available.

```
# Generate the required keys, certificates and configuration files.
./create-system
./create-server {server-name} {server-template} [nopass]
./create-client {client-name} {client-template} [nopass]
./create-crl
./delete {client-name|server-name}
./show {ca|crl|crt}
./change-pass {ca, client-name or server-name}

# Update and manage a local OpenVPN system.
./update-crl [RESTART]
./update-server {server-name} [CLEAN]
./update-client {client-name} [CLEAN]
./system {stop|start|restart|status} [client-name|server-name]
./system-logs {log-file-name} [FOLLOW]
./system-ipp

# Backup key, certificates and configuration.  
./update-thumbdrive

# Remove and restore keys for better security.
./remove-keys
./restore-keys

```

## License

This project is licensed under the GNU GPL v3 License - see the [LICENSE](LICENSE) file for details.