# Azure Kubernetes Service CheatSheet

## Cluster Operations

### Recover cluster from Failed State

The aks-preview Azure CLI extension (version 0.5.66+) now supports running az aks update -g <resourceGroup> -n <clusterName> without any optional arguments. This command will perform an update operation without making any changes, which can recover a cluster stuck in a failed state.

```sh
az aks upgrade  -g <resourceGroup> -n <clusterName> --kubernetes-version  1.22.15

-- or
az resource update --name $ClusterName --resource-group $RgName --resource-type Microsoft.ContainerService/managedClusters --debug
# az resource show --name $ClusterName --resource-group $RgName --resource-type Microsoft.ContainerService/managedClusters

-- or (requires aks preview extension)
az aks update -g <resourceGroup> -n <clusterName>

```