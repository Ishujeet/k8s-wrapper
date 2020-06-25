# k8s-wrapper

Small wrapper scripts to around `kubectl` to ease working with `Kubernetes Resources`.

## Usage

Scripts can be found in [bin](bin)

```
* ks :- This script is used to get Kubernetes Service Resource and describe it
* kp :- This script is used to get Kubernetes Pods Resource and describe it
* ki :- This script is used to get Kubernetes Ingress Resource and describe it
```

### ks Usage

```shell
ks <search term> [-h] [-d] [-n] [-a]-- search for Kubernetes Service, display and describe it

where:
    -h, --help           Show this help text
    -d, --describe       Describe the Kubernets service
    -n, --namespace      The Kubernetes namespace where the pods are located (defaults to "default")
    -a, --all-namesapces All Kubernetes namespaces

examples:
    # Display service in default namespace, which is "default"
    ks service-name

    # Display service in given namespace
    ks service-name -n namespace

    # Display service in all namespaces
    ks service-name -a

    # Describe service in default namespace, which is "default"
    ks service-name -d

    # Describe service in given namespace
    ks service-name -n namespace -d

    # Describe service in given namespace
    ks service-name -a -d

    #Note: Make sure you have the selector in with "app=name" in your resources.
```

### kp Usage

```shell
kp <search term> [-h] [-d] [-p] [-n] [-a]-- search Kubernetes Pods, display and describe them

where:
    -h, --help           Show this help text
    -d, --describe       Describe the Kubernets Pods created latest
    -p, --pod            Describe particular pod
    -n, --namespace      The Kubernetes namespace where the pods are located (defaults to "default")
    -a, --all-namesapces All Kubernetes namespaces

examples:
    # Display the pods exists in defualt namespace, which is  "default"
    kp name

    # Display the pods exists in namespace provided here
    kp name -n namespace

    # Display the pods by given name in all namespaces
    kp name -a

    # Describe pod which is latest created in default namespace "default"
    kp name -d

    # Describe pod which is latest created in given namespace
    kp name -n namespace -d

    # Describe pod which is latest created in all namespaces
    kp name -a -d

    # Describe particular pod provided in default namespace "default"
    kp name -p pod-name
    kp -p pod-name

    # Describe particular pod provided in given namespace
    kp name -n namespace -p pod-name
    kp -n namespace -p pod-name

    # Describe pod which is latest created in all namespaces
    kp name -p pod-name -a
    kp -p pod-name -a

    #Note: Make sure you have the selector in with "app=name" in your resources.
```

### ki Usage

```shell
ki <search term> [-h] [-d] [-n] [-a]-- search for Kubernetes Ingress, display and describe it

where:
    -h, --help           Show this help text
    -d, --describe       Describe the Kubernets ingress
    -n, --namespace      The Kubernetes namespace where the pods are located (defaults to "default")
    -a, --all-namesapces All Kubernetes namespaces

examples:
    # Display ingress in default namespace, which is "default"
    ki ingress-name

    # Display ingress in given namespace
    ki ingress-name -n namespace

    # Display ingress in all namespaces
    ki ingress-name -a

    # Describe ingress in default namespace, which is "default"
    ki ingress-name -d

    # Describe ingress in given namespace
    ki ingress-name -n namespace -d

    # Describe ingress in all namespaces
    ki ingress-name -a -d

    #Note: Make sure you have the selector in with "app=name" in your resources.
```

### Requirements

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install jq

```
pip install jq
```
