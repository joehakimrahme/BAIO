BAIO - Blogstrap All In One
===========================

This playbook will deploy a blogstrap blog and serve it over the web
with nginx and gunicorn. It is not production ready yet, there are
still some security concerns. The playbook is meant only as a
technology preview so you can get started with Blogstrap.

Pre-requisites
--------------

Make sure you have [Ansible](https://www.ansible.com/)
installed. Ansible can be executed from any machine on the network,
ideally from inside a virtualenvironment. I usually run ansible on my
laptop.


You need to have the IP of a machine you can reach over SSH. As of
now, this playbook only supports CentOS 7. Set up key-based
authentication to make your life easier.

You need to have a Blogstrap blog published somewhere accessible over HTTP. The playbook will clone it on your target host.


Getting started
----------------

Start by cloning this repository, then edit the file `hosts` to match
this:

``` ini
[blogserver]
X.X.X.X
```
(replace `X.X.X.X` with the IP address of your machine).

Then edit the file `group_vars/all` to include the URL of your blog
repository.

From the root of this repository, run this:

``` shell
$ ansible-playbook -i hosts site.yml
```

