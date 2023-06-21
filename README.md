# kube-requests-checker

kube-requests-checker - Show containers without requests set for CPU, Memory, or both, in a Kubernetes cluster

## Requirements

* kubectl
* jq
  
## Usage

Run:

```
./kube-requests-checker.sh -h
```

Output:

```
kube-requests-checker - Show containers without requests set for CPU, Memory, or both, in a Kubernetes cluster

Usage: ${CLI_NAME} <options>

-n | --namespace <namespace>   : Check containers in one specific namespace                                     Default: All non "kube-system" namespaces
-l | --level <level>           : Group results by "pod" or "controller". "pod" also returns Pod QoS.            Default: controller
-i | --include-kube-system     : Include "kube-system" namespace. Cannot be used when specifying one namespace.                                   
-h | --help                    : Show CLI usage

Example:
========
Show all containers with no requests set in the cluster in all non kube-system namespaces.                      $ ${CLI_NAME}
Show all containers with no requests set in the cluster, in all namespaces, including kube-system.              $ ${CLI_NAME} -i
Show all containers with no requests set in namespace foo, and group by pod.                                    $ ${CLI_NAME} -n foo -l pod
```
