# Basics
* [Object Management](#object-management)
* [Names and IDs](#names-and-ids)
* [Labels and Selectors](#labels-and-selectors)

## Object Management
There are 3 (or 4?) ways to invoke the creation and modification of Kubernetes objects:
* **Imperative inline commands**
    ```
    kubectl create deployment nginx --image nginx
    ```
    * Only use for dev environments, because it is hard to track

* **Impreative configuration files**
    ```
    kubectl create -f nginx.yaml
    ```
    * Involves the creation of yaml config files, but each change is manually applied
    * Live changes are not reflected in the config files
    
* **Declarative configuration files**
    ```
    kubectl diff -R -f configs/
    kubectl apply -R -f configs/
    ```
    * Similar to using imperative config files, but on directories
    * Treats the objects like it actually belongs in a system
    * Live changes are not reflected in the config files

* **Using GitOps**
    * Would recommend, because solves the issue of config drift that still exists in all previous methods

## Names and IDs
* Names are unique for objects of the same type within namespaces
* UIDs are globally unique within a cluster despite different object types

## Labels and Selectors
### Labels
* Labels are part of an object's metadata
* Labels are intended to be meaningful for the user, but is not actually used in any kind of processing by Kubernetes
* Labels are denoted as key value pairs

### Selectors
* 