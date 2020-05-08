## How to use this image

***

`docker run --name samba -d -p 445:445 -v /path/to/smb.conf:/etc/samba/smb.conf -v /path/to/media:/home moesnow/samba`

## Examples configuration

***

### smb.conf

```smb.conf
 [global]
    workgroup = WORKGROUP
    netbios name = Samba
    map to guest = bad user
    directory mask = 0777
    browseable = yes
    writeable = yes
    guest ok = yes
    guest only = yes
    read only = no
    dns proxy = no
    disable netbios = yes
 
 [Shares]
    path = /home/Shares

 [Downloads]
    path = /home/Downloads
```
