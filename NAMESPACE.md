# Namespaces

<h1>Namespace Defination</h1> An isolated environment for resources which can be seen only at that namespace isolated and separated from other namespaces. Files and Directory's are not affected by this it can be seen in cluster only resources get isolated which can only seen by specifying the particular namespace

<h1>Namespace Creation</h1>

    kubectl create ns (name of namespace)
    or
    kubectl create namespace (name of namespace)

<h1>See Created Namespace</h1>

    kubectl get namespace 
    or 
    kubectl get ns 
    
<h1>Imperitive 
<br>
<h1>Creating Resource In Namespace</h1>

    kubectl apply -f (name of yaml file) -n (name of namespace) 

-n (name of namespace) : can be used everywhere 
<br>

  Example:

         kubectl get pods -n (name of namespace)
         kubectl run (name of pod) --image=(image name nginx) -n (name of namespace
         kubectl logs (Resource) -n (name of namespace)
<h1>Declarative
<br>
<h1>Strecutre of YAML</h1>

    apiversion:
    kind:
    metadata:
      name:
      namespace:

In yaml apiversion, kind, metadata is default to create any resource in namespace put the namespace in metadata section 

<h1>To Set Any Namespace As Default Namespace & Switch Namespace Quickly</h1>

    kubectl config set-context --current --namespace=(name of namespace)

<h1>To See Current Working Namespace</h1>

    kubectl config view --minify | grep namespace 
    or
    kubectl config current-context
    
<h1>To See All Resources In Different Namespaces</h1>

    kubectl get all --all -namespace 

<h1>Delete Namespace</h1>

    kubectl delete ns (name of namespace)

<h1>Watch Resources Live</h1>

    kubectl get pods -n dev -w

<h1>List Resources Supported in Namespace</h1>

    kubectl api-resources --namespaced=true

  Cluster-wide resources:

    kubectl api-resources --namespaced=false
