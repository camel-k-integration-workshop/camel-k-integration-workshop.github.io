+++
title = "Prepare your cluster"
weight = 5
+++

## Cluster Preparation

Before you start you have to install a number of operators you'll use during the workshop. These two are `Red Hat Integration - Camel K` for providing Camel services in your cluster and `Red Hat OpenShift Serverless` to make our application truly serverless and scalable. But fear not, both are managed by Kubernetes [operators](https://cloud.redhat.com/learn/topics/operators) on OpenShift.

### Install and prepare Camel K Operator

- In the Web Console, go to **Operators > OperatorHub** and search for `Red Hat Integration - Camel K` (You may need to disable search filters)

{{< figure src="../images/camelk_operator.png?width=15pc&classes=border,shadow" title="Click image to enlarge" >}}

- Install the `Red Hat Integration - Camel K Operator` with default settings

{{% notice tip %}}
Make sure **Installation Mode** is set to **All namespaces on the cluster**
{{% /notice %}}



### Install and prepare OpenShift Serverless operator

- In the Web Console, go to **Operators > OperatorHub** and search for `Red Hat OpenShift Serverless` (You may need to disable search filters)

{{< figure src="../images/serverless_operator.png?width=15pc&classes=border,shadow" title="Click image to enlarge" >}}

- Install the `Red Hat OpenShift Serverless Operator` with default settings

{{% notice tip %}}
Make sure **Installation Mode** is set to **All namespaces on the cluster**
{{% /notice %}}



### Login to OpenShift from your local machine 

- If you don't already have the oc client installed, you can download the matching version for your operating system [here](https://docs.openshift.com/container-platform/4.8/cli_reference/openshift_cli/getting-started-cli.html)
- Log into your OpenShift Webconsole with you cluster admin credentials 
- In the top right corner, click on your username and then **Copy login command** to copy your login token

{{< figure src="../images/copy_login_command.png?width=50pc&classes=border,shadow" title="Click image to enlarge" >}}

- On your local machine either: 
  * open a terminal and log in with the `oc` command you copied **OR**
  * use the integrated terminal in VSCode to log in with the `oc` command you copied  

Your cluster is now prepared for the next step, proceed to the **Task 1 - Hello World**.