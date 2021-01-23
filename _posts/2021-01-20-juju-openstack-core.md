---
layout: post
title:  "juju openstack core"
date:   2021-01-11 18:21:00 +0000
categories:
---
# This post is WIP and will be updated eventually

## Installing Openstack Core with juju
This assumes you have MAAS and Ubuntu 20.04 already setup and installed

{% highlight shell %}
sudo snap install --classic juju
sudo snap install --classic charm
sudo snap install vault
sudo snap install openstack

charm pull cs:openstack-base
cd openstack-base

vim bundle.yml

juju bootstrap --constraints tags=juju --bootstrap-constraints tags=controller maas

juju deploy ./bundle.yaml

watch -c juju status --color
{% endhighlight %}