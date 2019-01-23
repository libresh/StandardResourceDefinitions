# Standard Resource Definitions

This repo contains a list of Standard Resource Definitions (SRD) in opposition to Custom Resource Definitions (CRD).

## Why is this needed

The kubernetes resource model is beautiful. With the addition to CRDs, it is an extraordinary API to build anything cloud.

We also know that a standard is always good to enable an ecosystem to thrive.

Let's take 2 examples Ingresses and MySQL.

### Ingress example

Ingress is definied upstream, and the implementation is left to the Kubernetes ecosystem.
We have doznes of implementations, and the adoption is broad as the public is confident that
the decision of using one can easily be reversed, with minimum effort.
Of course all implementations are not equal, but the base is, that's why the effort of changing ingress
is lower because we have a standard.

### MySQL example

MySQL is not currently defined upstream. To my knowledge, there are x different MySQL CRD with the corresponding
controller:
 - kubedb
 - crossplane
 - galera
 - operator
 - helm
 - Azure SC
 - Amazon SC
 - AWS Service Operator

You have 3 negative effects:
 - if you want to build a higher construct that depends on MySQL (like an helm chart for an open source lamp app),
it is really challenging to develop one that will accomodate the needs of all users.
 - if you want to build an app that is multicloud, and leverage cloud services, it is challenging.
 - it is more complexe to migrate from one implementation to another.

To solve these challenges, this repo is an attempt of storing a list of SRDs so that implementations can rely on.
On another nice side effect is that it is a nice way to discover controllers you were not aware.
