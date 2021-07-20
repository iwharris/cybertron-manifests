https://jonathangazeley.com/2021/01/05/using-truenas-to-provide-persistent-storage-for-kubernetes/

# Notes

The http portion requires the root user - ApiKey method works though

Can use https connection (see yaml file)

If using a non-root user for SSH, must add them to sudoers file (visudo)

Make sure to update permissions on the datasets so that the owner matches the user that is SSHing

Can use SSH key authentication instead of password

NFS shares are not necessary - just enable the nfs service in TrueNAS

Use `microk8s helm3` for the helm commands