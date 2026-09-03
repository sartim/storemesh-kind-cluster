# StoreMesh Kind cluster

`storemesh.yaml` defines the local two-node development cluster used to test
the StoreMesh deployment path: one control-plane node and one worker. This is
the minimum topology that keeps a dedicated worker available while reducing
Docker/Kind overhead on a developer machine. Workloads still scale by pod
replica within the available node capacity.

The configuration repository change does not alter an existing cluster. Kind
does not support shrinking a running cluster in place; the two-node profile
applies the next time the developer intentionally creates a new cluster.

```sh
kind create cluster --config storemesh.yaml
```
