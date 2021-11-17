# Open a terminal in Jupyterlab

# Clone dask-tutorial with this terminal

```bash
git clone https://github.com/dask/dask-tutorial.git

cd dask-tutorial
```

# Only for the machine learning example (number 8)

## Put a worker spec.yaml in there

## Replace 
```python
from dask.distributed import Client

client = Client(n_workers=4)
```

## By

```python
import dask
import dask.distributed  # populate config with distributed defaults
import dask_kubernetes

dask.config.set({"kubernetes.worker-template-path": "worker-spec.yaml"})
dask.config.set({"distributed.dashboard.link": "{JUPYTERHUB_SERVICE_PREFIX}proxy/{port}/status"})

from dask_kubernetes import KubeCluster

cluster = KubeCluster(deploy_mode='local') # Scheduler is started in the notebook process
cluster

cluster.scale(4)

from distributed import Client

client = Client(cluster)
client
```