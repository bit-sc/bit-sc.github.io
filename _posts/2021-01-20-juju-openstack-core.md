---
layout: post
title:  "Installing Openstack Core with juju"
date:   2021-01-11 18:21:00 +0000
categories:
---
# This post is WIP and will be updated eventually

## Deployment 

### Install and Setup Prerequisites
This assumes you have MAAS and Ubuntu 20.04 already setup and installed

{% highlight shell %}
sudo snap install --classic juju
sudo snap install --classic charm
sudo snap install vault
sudo snap install openstack

juju bootstrap --constraints tags=juju --bootstrap-constraints tags=controller maas
{% endhighlight %}

### Deploying Openstack Core 
{% highlight shell %}
charm pull cs:openstack-base
cd openstack-base

vim bundle.yml

juju deploy ./bundle.yaml

watch -c juju status --color
{% endhighlight %}