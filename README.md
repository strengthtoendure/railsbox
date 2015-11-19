# Rails Box

Vagrant box provisioned with Ansible to run Ruby on Rails applications.

Includes:
 - Ubuntu 14.04 LTS
 - Ruby 2.2.3 (via rbenv)
 - Most current version of Bundler & Rails at time of `vagrant up`
 - Mysql
 - Postgresql
 - Sqlite
 - Redis
 - Git

## Getting started

For new projects, clone this repo and run:
```
$ vagrant up
$ vagrant ssh
$ cd /vagrant
$ rails new blog
$ cd blog && rails s -b 0.0.0.0
#-b 0.0.0.0 needed to access 3000 outside of vagrant
```

For existing Rails projects copy the `Vagrantfile` and `ansible` directory to your Rails project directory and run:

```
$ vagrant up
$ vagrant ssh
$ cd /vagrant
$ rails s -b 0.0.0.0
```

## Configuration

Locate the `vars:` section inside `ansible/main.yml` to change which version of Ruby you would like installed.

Edit `ansible/files/gemrc` to change default gem install options

Edit `Vagrantfile` to change CPU and Memory settings.

## License

MIT

## Credit

Josh Frye @joshfng on GitHub and Twitter
