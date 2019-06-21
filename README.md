# Beyond the Basics: Istio and DataDog on IBM Cloud Kubernetes Service

[Istio](https://www.ibm.com/cloud/info/istio) is an open platform to connect, secure, control and observe microservices, also known as a service mesh, on cloud platforms such as Kubernetes in IBM Cloud Kubernetes Service and VMs. With Istio, You can manage network traffic, load balance across microservices, enforce access policies, verify service identity, secure service communication and observe what exactly is going on with your services.

In this course, you can see how to install Istio alongside microservices for a simple mock app called [Guestbook](https://github.com/IBM/guestbook). When you deploy Guestbook's microservices into an IBM Cloud Kubernetes Service cluster where Istio is installed, you can choose to inject the Istio Envoy sidecar proxies in the pods of certain microservices.

## Objectives

After you complete this course, you'll be able to:

* Download and install Istio in your cluster
* Deploy the Guestbook sample app
* Use metrics, logging and tracing to observe services
* Set up the Istio Ingress Gateway
* Perform simple traffic management, such as A/B tests and canary deployments
* Secure your service mesh
* Enforce policies for your microservices

## Prerequisites

You must you must have a Pay-As-You-Go, or Subscription [IBM Cloud account](https://console.bluemix.net/registration/) to complete all the modules in this course.

You must have [already created a Standard cluster](https://console.bluemix.net/docs/containers/container_index.html#container_index) in IBM Cloud Kubernetes Service. **FREE Cluster is not supported for this lab**

You should have a basic understanding of containers, IBM Cloud Kubernetes Service, and Istio. If you have no experience with those, take the following courses: 1. [Get started with Kubernetes and IBM Cloud Kubernetes Service](https://cognitiveclass.ai/courses/kubernetes-course/) 2. [Get started with Istio and IBM Cloud Kubernetes Service](https://cognitiveclass.ai/courses/get-started-with-microservices-istio-and-ibm-cloud-container-service/)

## Workshop setup

* [Exercise 1 - Accessing a Kubernetes cluster with IBM Cloud Kubernetes Service](exercise-1.md)
* [Exercise 2 - Installing Istio](exercise-2.md)
* [Exercise 3 - Deploying Guestbook with Istio Proxy](exercise-3.md)

## Creating a service mesh with Istio

* [Exercise 4 - Observe service telemetry: metrics and tracing](exercise-4.md)
* [Exercise 5 - Expose the service mesh with the Istio Ingress Gateway](exercise-5.md)
* [Exercise 6 - Perform traffic management](exercise-6.md)
* [Exercise 7 - Secure your service mesh](exercise-7.md)
* [Exercise 8 - Enforce policies for microservices](exercise-8.md)

## Cleaning up the Workshop

We have a script that will remove [ibmcloud](https://console.bluemix.net/docs/cli/index.html#overview) at [here](https://raw.githubusercontent.com/svennam92/istio101/master/workshop/cleanup/clean_your_local_machine.sh) and unset your `KUBECONFIG` for you.

We have given you a [script](https://raw.githubusercontent.com/svennam92/istio101/master/workshop/cleanup/clean_your_k8s_cluster.sh) as a convenient way to remove Istio and the guestbook application from your instance.

**NOTE**: This puts your kubernetes cluster in a empty state, so do not run this on anything other then a place you are willing to loose everything.

