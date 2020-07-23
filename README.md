# CertifyMe

<a href="https://www.buymeacoffee.com/mjwhitta">🍪 Buy me a cookie</a>

This tool is for quickly generating a root CA and client/server
certificates.

## Usage

To use this tool, generate a `certifyme.conf` file:

```
$ certify --sample-config >certifyme.conf
```

and then edit the variables to fit your needs.

**Note: If using the `--pki` flag or `CERTIFYME_PKI` env var, the
default `certifyme.conf` would be located in the specified directory**

Certificates can be created with the following commands:

```
# Creates a CA if it doesn't already exist
$ certify

# Create server certs
$ certify server1 server2 serverN

# Create client certs
$ certify --client client1 --client client2 --client clientN

# Create Diffie-Hellman parameters
$ certify --dh

# Create CA, client certs, Diffie-Hellman params, and server certs
# all-in-one
$ certify -c client1 -c clientN --dh server1 serverN
```

**Note: Use the fqdn for server names**

The root CA will be in `ca`, the client/server certificates are in
`certs`, private keys are in `private`, and Diffie-Hellman parameters
are in `dh`.

To wipe a PKI and start over use the following command:

```
$ certify --wipe
```

## Installation

You can install the `certify` script to `/usr/local/bin` with the
following command:

```
$ ./installer -d /usr/local/bin
```
