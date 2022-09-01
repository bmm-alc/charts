# ddclient

![Version: 3.2.1](https://img.shields.io/badge/Version-3.2.1-informational?style=flat-square) ![AppVersion: 3.9.1](https://img.shields.io/badge/AppVersion-3.9.1-informational?style=flat-square)

Perl client used to update dynamic DNS entries for accounts on Dynamic DNS Network Service Providers

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/djjudas21/charts/issues/new/choose)**

## Source Code

* <https://github.com/ddclient/ddclient>
* <https://hub.docker.com/r/linuxserver/ddclient>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| `http://bjw-s.github.io/helm-charts/` | common | 4.5.2 |

## TL;DR

```console
helm repo add djjudas21 https://djjudas21.github.io/charts/
helm repo update
helm install ddclient djjudas21/ddclient
```

## Installing the Chart

To install the chart with the release name `ddclient`

```console
helm install ddclient djjudas21/ddclient
```

## Uninstalling the Chart

To uninstall the `ddclient` deployment

```console
helm uninstall ddclient
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/bjw-s/helm-charts/blob/main/charts/library/common/values.yaml) from the [common library](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install ddclient \
  --set env.TZ="America/New York" \
    djjudas21/ddclient
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install ddclient djjudas21/ddclient -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/bjw-s/helm-charts/tree/main/charts/library/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config | string | `"# This is the configuration for ddclient\n# Inorder for it to function you need to set it up\n# e.g. this is the config for Cloudflare\ndaemon=600\nuse=web\nweb=dynamicdns.park-your-domain.com/getip\nprotocol=cloudflare\nssl=yes\nttl=1\nlogin=${CF_EMAIL}\npassword=${CF_GLOBAL_APIKEY}\nzone=${DOMAIN}.${TLD}\n${DOMAIN}.${TLD}\n"` |  |
| env | object | `{}` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"linuxserver/ddclient"` |  |
| image.tag | string | `"version-v3.9.1"` |  |
| ingress.enabled | bool | `false` |  |
| probes.liveness.enabled | bool | `false` |  |
| probes.readiness.enabled | bool | `false` |  |
| probes.startup.enabled | bool | `false` |  |
| service.enabled | bool | `false` |  |
| strategy.type | string | `"Recreate"` |  |

## Support

* Open an [issue](https://github.com/djjudas21/charts/issues/new/choose)

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)