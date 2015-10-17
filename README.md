# provisioning

Scripts &amp; Tools for Physical or Virtual Server Provisioning.

## Kickstarts

[Kickstart files](https://en.wikipedia.org/wiki/Kickstart_%28Linux%29) are pretty handy to automate
and unify RHEL/CentOS installations. For non-trivial and more complicated configurations, however,
it is always a challenge to easily verify the configuration file. Especially when using
[kickstart files](https://en.wikipedia.org/wiki/Kickstart_%28Linux%29) within some special software
for provisioning, like [Cobbler](https://en.wikipedia.org/wiki/Cobbler_%28software%29).
If this is the case, certain variables (e.g. hostname, network configuration, etc.) are set in that
layer, which makes the actual [kickstart files](https://en.wikipedia.org/wiki/Kickstart_%28Linux%29)
quite abstract and almost impossible to render outside that specific provisioning environment.

The aim in this repository is exactly that: to help rendering [kickstart files](https://en.wikipedia.org/wiki/Kickstart_%28Linux%29)
by adding the missing variables and altering as little as possible.

## Build CentOS/RHEL 6.x Kickstart

Edit the `variables` file and run `build_ks.sh` with the kickstart template:
~~~
$ ../tools/build_ks.sh centos6.tml
~~~


## TODOs

 - use `variables` file as parameter for build script
 - omit `#include "variables"` and `SNIPPET()` function definition in the actual [kickstart file](https://en.wikipedia.org/wiki/Kickstart_%28Linux%29)
 - centos6: Disable IPv6 as an option 
 - centos6: Add hostname on `/etc/hosts`


## References

 - [RHEL 6 Kickstart Guide](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Installation_Guide/s1-kickstart2-options.html)
