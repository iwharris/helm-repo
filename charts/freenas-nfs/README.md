# Notes

Taken from https://jonathangazeley.com/2021/01/05/using-truenas-to-provide-persistent-storage-for-kubernetes/

- The http portion requires the root user - ApiKey method works though
- Can use https connection if you have a cert
- If using a non-root user for SSH, must add them to sudoers file (`visudo`)
- Make sure to update permissions on the datasets so that the owner matches the user that is SSHing
- Can use SSH key authentication instead of password
- NFS shares are not necessary - just enable the nfs service in TrueNAS
- Use `microk8s helm3` for the helm commands.
- If getting sudo errors on the provisioner, ssh to freenas and use the CLI to update the user:

```bash
query select=id,username,sudo,sudo_nopasswd
update id=38 sudo=true sudo_nopasswd=true
```
