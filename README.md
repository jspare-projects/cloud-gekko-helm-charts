# Cloud Gekko Open Source Helm Chart

The [Cloud Gekko Helm charts](https://github.com/jspare-projects/cloud-gekko-helm-charts) enable you to deploy Jspare Cloud Gekko Platform services on Kubernetes for development, test, and proof of concept environments.

### Installation Steps

Installing using the `upgrade` command:

```
# helm upgrade --install [RELEASE] [CHART]
helm upgrade --install platform ./helm/jspare-gekko-platform
```

Installing an unstable version of Gekko:

```
# helm upgrade --install [RELEASE] [CHART]
helm upgrade --install platform ./helm/jspare-gekko-platform --set gekko.version=unstable
```

### Configuration

The following table lists the configurable parameters of the gekko chart and their default values.

|              Parameter               |                             Description                             |                       Default                       |
| ------------------------------------ | ------------------------------------------------------------------- | --------------------------------------------------- |


Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

In terms of Memory resources you should make sure that you follow that equation:

- `${role}HeapSize < ${role}MemoryRequests < ${role}MemoryLimits`

The YAML value of cluster.config is appended to elasticsearch.yml file for additional customization ("script.inline: on" for example to allow inline scripting)

### Uninstall:

If you installed Gekko using the helm command, uninstall with the following command:

```
helm delete --purge platform
```