# dealing-with-selinux
tricks for dealing with selinux

**To see what label was applied to volume mounts when a podman container was created do this:**  
```
podman inspect homebridge | grep -i mountlabel
```
Output will look like this:
```
  "MountLabel": "system_u:object_r:container_file_t:s0:c472,c481",
```
To apply a context to files / directories:
```
chcon -Rv system_u:object_r:container_file_t:s0:c472,c481 /path/
```


