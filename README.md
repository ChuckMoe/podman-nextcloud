# Image
The image used was created by [Nextcloud](https://hub.docker.com/_/nextcloud). For all variable descriptions, go there.

# Volumes
Change the volumes.hostPath.path to the directory where you want to save and access all the data available to Nextcloud. If you do not want or need direct access, you can instead use:

```yaml
volumes:
  - name: data
    persistentVolumeClaim:
          claimName: nextcloud-data
```

# Commands

Start Nextcloud
```bash
podman play kube --configmap=secrets/nextcloud.yaml,secrets/db.yaml pod.yaml
```

Stop Nextcloud
```bash
podman play kube --down pod.yaml
```

To update Nextcloud, aka. use the newest container, just stop and start again.
