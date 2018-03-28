# CertifyMe

This tool is for quickly generating a root CA and client/server
certificates. To use this tool, copy `params.sample` to `params` and
then edit the variables in it to fit your needs. Certificates can be
created with the following commands:

```
# Creates a CA if it doesn't already exist
$ ./certify

# Create server certs
$ ./certify server1 server2 serverN

# Create client certs
$ ./certify --client client1 --client client2 --client clientN

# Create Diffie-Hellman parameters
$ ./certify --dh

# Create CA, client certs, Diffie-Hellman params, and server certs
# all-in-one
$ ./certify -c client1 -c clientN --dh server1 serverN
```

**Note: Use the fqdn for server names**

The root CA will be in `ca`, the client/server certificates are in
`certs`, private keys are in `private`, and Diffie-Hellman parameters
are in `dh`.

**Note: If using the `--pki` flag, the `params` file must be in the
specified directory**
