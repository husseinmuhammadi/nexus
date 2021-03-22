# Nexus Repository 

## Install Nexus Server

There are two general approaches to handling persistent storage requirements with Docker. See Managing Data in Containers for additional information.

Use a docker volume. Since docker volumes are persistent, a volume can be created specifically for this purpose. This is the recommended approach.

```
$ docker volume create --name nexus-data
$ docker run -d -p 8081:8081 --name nexus -v nexus-data:/nexus-data sonatype/nexus3
```

### Admin Password
The initial password for the admin user can be found in an admin.password file found in the $data-dir directory after starting the server.

## Configuring nexus as a npm repo
What we will do:
– create a private (hosted) repository for our own packages
– create a proxy repository pointing to the official registry
– create a group repository to provide all the above repos under a single URL

https://blog.sonatype.com/using-nexus-3-as-your-repository-part-2-npm-packages
