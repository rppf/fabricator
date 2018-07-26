# Fabricator

[![Travis (.org)](https://img.shields.io/travis/rppf/fabricator.svg?style=flat-square)](https://travis-ci.org/rppf/fabricator)
[![License](https://img.shields.io/github/license/rppf/fabricator.svg?style=flat-square)](LICENSE)

This role will install the following:

- PHP 7.1
- NodeJS 8.x (including npm and yarn)
- MariaDB 10.2
- Caddy
- Redis 4.0.8

This is role is successfully tested on Centos 7.

## How to use

Before executing Weaver, you must first check the default values of Weaver located in **`defaults/main.yml`**. You can change the values if you want.

Follow these steps if you're going to install packages to other server/s:

1. Create a SSH Key by running this command.

```shell
ssh-keygen -t rsa
```

2. Then copy the ssh key. **`ssh-copy-id user@hostname`**. For this example I will be using user **root** and a hostname **localhost**.

```shell
ssh-copy-id root@localhost
```

3. Git clone this repo.

4. Then inside the Weaver directory, create a playbook, inventory file, and an ansible configuration file.
  - Name your playbook file **`playbook.yml`** or anything you want. [Copy this into your playbook file](https://gist.github.com/rppf/86cb22d52b65add74f6b0a89162d2777 "Copy this into your playbook file")

  - Name your inventory file **`hosts`** or **`inventory`**. [Copy this into your inventory file](https://gist.github.com/rppf/d82467a7dd36b784a945786d22cb10ab "Copy this into your inventory file")

  - Add a file named **`ansible.cfg`**. [Copy this into your ansible.cfg](https://gist.github.com/rppf/1a33bb5d6baa381a18ac92831270bc3e "Copy this into your ansible.cfg")

5. Then run this command inside the directory of Weaver

```shell
ansible-playbook -K playbook.yml
```

## Alternative

If you're going to run Ansible in you local machine. Run this command in your terminal. You can skip steps 1 & 2 in perfoming this command.

```shell
ansible-playbook playbook.yml --connection=local
```

You can also choose what to be installed. The main task is located in **`tasks/main.yml`**.Just uncomment **`#`** the task you don't want to be installed.
![](https://i.imgur.com/MdFQC3X.png)

## License

MIT

## Notes

If you are new to Ansible. [Read their docs](https://docs.ansible.com/ansible/2.5/index.html "Read their docs").
If your looking for tutorials about Ansible. Check this [youtube channel](https://www.youtube.com/watch?v=icR-df2Olm8&list=PLFiccIuLB0OiWh7cbryhCaGPoqjQ62NpU "youtube channel").
