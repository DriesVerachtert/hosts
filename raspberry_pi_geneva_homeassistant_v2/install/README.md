# user-data

Setup pi at install time.

```
export DRIESPASSWORD=$(dpass systems/genevapiv2/dries/password | mkpasswd -m sha-512 -s)
export SSHPUBLICKEY=$(dpass systems/genevapiv2/ssh-key-public)
export ROOTPASSWORD=$(dpass systems/genevapiv2/root/password | mkpasswd -m sha-512 -s)
cat user-data-template.txt | sed "s|DRIESPASSWORD|${DRIESPASSWORD}|g; s|SSHPUBLICKEY|${SSHPUBLICKEY}|g; s|ROOTPASSWORD|${ROOTPASSWORD}|g;" > user-data
cp user-data network-config /Volumes/CIDATA/
```

cloud-init schema --system
alma
