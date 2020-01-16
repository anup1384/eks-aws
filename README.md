# Eks-AWS

### Table of Contents

* [Pre-Requisites](#Pre-requisites)
* [Starting Cluster Creation](#starting-cluster-creation)
  * [Script Steps](#script-steps)
* [Cleanup](#Cleanup)
  * [Delete cluster](#delete-cluster)


# Pre-requisites

* `awscli` ([reference](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html))
* `aws-iam-authenticator` ([reference](https://docs.aws.amazon.com/eks/latest/userguide/install-aws-iam-authenticator.html))
* `eksctl (0.1.18)` ([reference](https://github.com/weaveworks/eksctl))
* `helm` ([reference](https://docs.helm.sh/using_helm/#installing-helm))



<a id="starting-cluster-creation">

# Starting Cluster Creation

To create a cluster start the script deploy.sh

You should especify one environment:
- nonprod
- mgmt
- prod

```shell 
./deploy.sh nonprod|mgmt|prod
```


## Get cluster access

To get access to a cluster, use the command:
```shell 
eksctl utils write-kubeconfig --name cluster-name
```


# Cleanup

<a id="delete-cluster">

### Delete cluster
```shell
CLUSTER_NAME="nonprod"
eksctl delete cluster --name ${CLUSTER_NAME}
```
For mode details:-

https://medium.com/faun/create-a-kubernetes-cluster-on-amazon-eks-261336b89e17
