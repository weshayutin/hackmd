---
title: 'Lab deployment with TripleO-QuickStart'
disqus: tripleo
---

Lab deployment with TripleO-Quickstart
===


## Table of Contents

[TOC]

## Beginners Guide

If you are a total beginner to this, start here!

1. Visit https://docs.openstack.org/tripleo-quickstart/latest/
2. Visit https://docs.openstack.org/tripleo-docs/latest/ci/index.html


Lab setup for TripleO OpenStack Train release
---
> Create a user

```Shell=
useradd oooq
echo "Redhat123" | passwd --stdin oooq

# Needed for quickstart.sh --install-deps
echo "oooq ALL=(root) NOPASSWD:ALL" | sudo tee -a /etc/sudoers.d/oooq
sudo chmod 0440 /etc/sudoers.d/oooq
```
> As the user create ssh keys


```Shell=
ssh-keygen -f ~/.ssh/id_rsa -t rsa -N ''
ssh-copy-id root@127.0.0.2
```

> Download quickstart.sh and execute
```Shell=
curl -O https://raw.githubusercontent.com/openstack/tripleo-quickstart/master/quickstart.sh
chmod +x quickstart.sh
./quickstart.sh --tags all --release centosci/master-current-tripleo 127.0.0.2
```

> Only install the undercloud, and setup for an overcloud deployment
```Shell=
./quickstart.sh --release centosci/master-current-tripleo 127.0.0.2
```


## FAQ

:::info
**Find this document incomplete?** Leave a comment!
:::
:::info
source: https://hackmd.io/UZPFdivCSAm18jTLDBSdfg?both
:::

###### tags: `Templates` `Documentation`
