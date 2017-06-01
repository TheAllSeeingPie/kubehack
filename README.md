# Kubernetes Hack Night

## Google Cloud Setup

* Create an account and project on [Google Cloud Platform](https://cloud.google.com/)
  * NB: You will need to enter payment details, though new accounts are given $300 credits on the platform for the next 12 months and it will not charge after this period (according to Google). However, we recommend that you take precautions and destroy your cluster after you are finished.
* Navigate to the Google Container Engine dashboard in the Products & services navigation pane on the left hand side.
* Click the 'Create Cluster' button to open the cluster creation wizard.
  * Don't worry about most of the fields on this form, just give it a name and set the amount of nodes to 5 or less(6+ starts to charge you) and click 'Create'.

## Local Setup

* Install [Google Cloud SDK](https://cloud.google.com/sdk/)
  * Move the SDK somewhere sensible (and make sure your user is the owner of its parent folder). e.g. your home folder `~/google-cloud-sdk`
  * Run the `install.sh` script from the Google Cloud SDK folder to add the `gcloud` command to your PATH
* Run `gcloud components install kubectl` to install the Kubernetes CLI
* Run `gcloud init` to login to your Google Cloud Platform account. If it asks you to configure the Google Compute Engine, you don't need to do this.
* Open the Google Cloud Console, navigate to your cluster in the Container Engine, click the checkbox and then the 'Connect' button that appears. This should then prompt you with a command to configure kubectl with your cluster. (It should look something like `gcloud container clusters get-credentials cluster-1 \
    --zone europe-west1-c --project <project_id>`)
* Run `kubectl proxy`, then navigate to http://127.0.0.1:8001/ui to see the Kubernetes dashboard.

## The Application

So you've setup your lovely cluster and you're happy that it's stable. Unfortunately for you, you've just been informed that some pesky developers have built an application that they're confident is in full working order and ready for deployment.

Your manager has assigned the task of doing so to you, and he wants you to use your lovely new Kubernetes cluster. It's a simple chat application called Kubechat where like-minded individuals can get together online to discuss their favourite topics like trainspotting or watching Scrap Heap Challenge reruns on Dave.

You can watch your pods going up and down with the following command:
`kubectl get pods -w --all-namespaces`

### Challenge 1

Let's get a pod running.

`kubectl run nginx --image=nginx --port=80`

You should be able to run `kubectl get pods` now and see your new nginx container running on the cluster.



### Challenge 2



## Useful stuff

* [Kubernetes by Example](http://kubernetesbyexample.com/)
* [kubectl cheatsheet](https://kubernetes.io/docs/user-guide/kubectl-cheatsheet/)

## Next Steps

Some ideas on things to look at next:

* [Next Steps](NEXTSTEPS.md)

## Resources

* [Tools](resources/tools.md)
* [Tutorials](resources/tutorials.md)
* [Platforms](resources/platforms.md)
* [Community](resources/community.md)
* [Monitoring](resources/monitoring.md)
