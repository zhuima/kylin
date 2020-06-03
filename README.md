php ci/cd
=========

[![Ansible 2.7](https://img.shields.io/badge/ansible-2.7-yellow.svg)](https://www.ansible.com/)


## 使用前置条件

- 发布机器和代码托管平台信任建立(需要拉取代码的权限)
- 发布机器和rs机器之间的互信(需要传输文件)
  - 发布机器跟自己也要互信(基于key的)
- 发布机器上和rs机器上对应的父目录需要提前创建并确保权限是正确的
- php-deploy 请放到ansible的roles目录下，确保可以识别到


## 使用

```python
cd demo
ansible-playbook -i hlists deploy.yml -e "pname=php-laravel-hello-world env=dev branch=master git_repo=https://github.com/niwasawa/php-laravel-hello-world laravel_releases=3 smoketest_url=http://10.10.20.33:8877"
```