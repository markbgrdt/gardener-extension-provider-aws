# Compatibility

This file lists known compatibility issues with other Gardener components.


| AWS Extension | Gardener | Action | Notes |
| ----- | ----- | --- |  --------------- |
| `<= v1.15.0` | `>v1.10.0` | Please update the provider version to `> v1.15.0` or disable the feature gate `MountHostCADirectories` in the Gardenlet. | Applies if feature flag `MountHostCADirectories` in the Gardenlet is enabled. Shoots with CSI enabled (Kubernetes version >= 1.18) miss a mount to the directory `/etc/ssl` in the Shoot API Server. This can lead to not trusting external Root CAs when the API Server makes requests via webhooks or OIDC.  |