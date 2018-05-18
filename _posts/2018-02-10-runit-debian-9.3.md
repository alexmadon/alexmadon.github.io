---
date: '2018-02-10T03:10:00.001-0700'
tags: linux pdf
---

on debian strech 9.3

https://github.com/chef-cookbooks/runit/pull/224


+  # debian 9+ ship with runit-systemd which includes only what you need for process supervision and not
+  # what is necessary for running runit as pid 1, which we don't care about.
   pkg_name = platform?('debian') && node['platform_version'].to_i >= 9 ? 'runit-systemd' : 'runit'


```
root@hp:/etc/sv# ps auwx  | grep runsvdir
root      2225  0.0  0.0   4212  1216 ?        Ss   19:59   0:00 runsvdir -P /etc/service log: ...........................................................................................................................................................................................................................................................................................................................................................................................................

```


https://medium.com/@gdm85/runit-as-your-init-on-ubuntu-16-xenial-55d18513aac0

http://kchard.github.io/runit-quickstart/

https://debian-administration.org/article/697/Using_runit_for_maintaining_services
