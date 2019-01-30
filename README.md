Followed this information:

https://jamielinux.com/docs/openssl-certificate-authority/index.html

The CA Cert is at the top level.  There is an intermediate cert in the intermediate folder.

You should generate new cert signings with the intermediate cert, not the top level one.

See the README.md file in the intermediate folder.

To create the Root and Intermediate CAs run these scripts in order.

./1_gen-root-key-cert

pw: ?????????

./2_gen-intermediate-key-cert

pw: ?????????

To clean things up and start over.

```
rm -f certs/*
rm -f newcerts/*
rm -f private/*
echo -n > index.txt
echo 1000 > serial
rm -f index.txt.attr.old
rm -f index.txt.old
rm -f serial.old
rm -f intermediate/csr/*
rm -f intermediate/certs/*
rm -f intermediate/newcerts/*
rm -f intermediate/private/*
echo -n > intermediate/index.txt
echo 1000 > intermediate/serial
```
