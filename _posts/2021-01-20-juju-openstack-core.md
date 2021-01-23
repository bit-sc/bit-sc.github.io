---
layout: post
title:  "juju openstack core"
date:   2021-01-20 13:11:00 -0500
categories:
---

# Installing Openstack Victoria with juju
This assumes you have MAAS and Ubuntu 20.04 already setup and installed

{% highlight bash %}
sudo snap install --classic juju
sudo snap install --classic charm
sudo snap install vault
sudo snap install openstack

charm pull cs:openstack-base
cd openstack-base

vim bundle.yml

juju bootstrap --constraints tags=juju --bootstrap-constraints tags=controller maas

juju deploy ./bundle.yaml
{% endhighlight %}