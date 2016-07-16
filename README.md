# Rails Box

Vagrant box provisioned Ruby on Rails applications. Built using [railsbox-packer](https://github.com/joshfng/railsbox-packer). You can find the box hosted on Atlas [here](https://atlas.hashicorp.com/joshfng/boxes/railsbox/)

Includes:
 - Ubuntu 16.04 LTS
 - Latest stable Ruby (via rbenv)
 - Most current version of Bundler & Rails
 - Mysql
 - Postgresql
 - Sqlite
 - Redis
 - Git

## Getting started

```
cd myrailsproject
curl -O https://raw.githubusercontent.com/joshfng/railsbox/master/Vagrantfile
vagrant up
vagrant ssh
cd /vagrant

#if you don't already have a rails app
rails new .

bundle
bundle exec rake db:create
bundle exec rake db:migrate
```

## Mysql
The mysql root password is `vagrant`

## License

MIT

## Credit

Josh Frye @joshfng on GitHub and Twitter
