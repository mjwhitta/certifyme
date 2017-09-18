# CertifyMe

This tool is for quickly generating a root CA and client/server
certificates. To use this tool, copy `params.sample` to `params` and
then edit the variables in it to fit your needs. Next run `./certify`
to generate a root CA. Finally, client/server certificates can be
created with commands like the following:

```
$ ./certify server
$ ./certify --client client
```

**NOTE:** You may need to adjust the common name before making a
certificate. You can either modify the `params` file or use the
`--common-name` flag.

You can create Diffie-Hellman parameters using the `--dh` flag.

The root CA will be in `ca`, the client/server certificates are in
`certs`, private keys are in `private`, and Diffie-Hellman parameters
are in `dh`.
