# Exercise 1 - Accessing a Kubernetes cluster with IBM Cloud Kubernetes Service

You must already have a [cluster created](https://console.bluemix.net/docs/containers/container_index.html#container_index). Here are the steps to access your cluster.

## Install IBM Cloud Kubernetes Service command line utilities

1. Install the IBM Cloud [command line interface](https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html#getting-started).
2. Log in to the IBM Cloud CLI.

   ```text
   ibmcloud login
   ```

   If you have a federated account, include the `--sso` flag.

   ```text
   ibmcloud login --sso
   ```

   If you have an api key, use:

   ```text
   ibmcloud login --apikey <apikey>
   ```

3. Install the IBM Cloud Kubernetes Service plug-in.

   ```text
   ibmcloud plugin install container-service
   ```

4. To verify that the plug-in is installed properly, run `ibmcloud plugin list`. The Container Service plug-in is displayed in the results as `container-service/kubernetes-service`.
5. Initialize the Container Service plug-in and point the endpoint to your region. For example when prompted, enter `5` for `us-east`.

   Example:

   ```text
   ibmcloud ks region-set
   Choose a region:
   1. ap-north
   2. ap-south
   3. eu-central
   4. uk-south
   5. us-east
   6. us-south
   Enter a number> 5
   ```

6. Install the `kubectl` Kubernetes CLI. Go to the [Kubernetes page](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-via-curl), and follow the steps to install the CLI.

## Access your cluster

Learn how to set the context to work with your cluster by using the `kubectl` CLI, access the Kubernetes dashboard, and gather basic information about your cluster.

1. Set the context for your cluster in your CLI. Every time you log in to the IBM Cloud Kubernetes Service CLI to work with the cluster, you must run these commands to set the path to the cluster's configuration file as a session variable. The Kubernetes CLI uses this variable to find a local configuration file and certificates that are necessary to connect with the cluster in IBM Cloud.

   a. List the available clusters.

   ```text
   ibmcloud ks clusters
   ```

   b. Set an environment variable for your cluster name:

   ```text
   export MYCLUSTER=<your_cluster_name>
   ```

   c. Download the configuration file and certificates for your cluster using the `cluster-config` command.

   ```text
   ibmcloud ks cluster-config $MYCLUSTER
   ```

   d. Copy and paste the output command from the previous step to set the `KUBECONFIG` environment variable and configure your CLI to run `kubectl` commands against your cluster.

   Example:

   ```text
   export KUBECONFIG=/Users/user-name/.bluemix/plugins/container-service/clusters/mycluster/kube-config-hou02-mycluster.yml
   ```

2. Get basic information about your cluster and its worker nodes. This information can help you manage your cluster and troubleshoot issues.

   a. View details of your cluster.

   ```text
   ibmcloud ks cluster-get $MYCLUSTER
   ```

   b. Verify the worker nodes in the cluster.

   ```text
   ibmcloud ks workers $MYCLUSTER
   ibmcloud ks worker-get <worker_ID>
   ```

3. Validate access to your cluster.

   a. View nodes in the cluster.

   ```text
   kubectl get node
   ```

   b. View services, deployments, and pods.

   ```text
   kubectl get svc,deploy,po --all-namespaces
   ```

## Clone the lab repo

1. From your command line, run:

   ```text
    git clone https://github.com/svennam92/istio101

    cd istio101/workshop
   ```

   This is the working directory for the workshop. You will use the example `.yaml` files that are located in the `workshop/plans` directory in the following exercises.

### [Continue to Exercise 2 - Installing Istio](exercise-2.md)

