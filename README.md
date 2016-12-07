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

#if you don't already have a rails app
rails new .

bundle
bundle exec rake db:create
bundle exec rake db:migrate
```

## Mysql
The mysql root password is `root`

## Postgresql
PG is installed, but you need to manually create a user and db if you want to use it
```
sudo -u postgres psql -c "CREATE ROLE MY_USER LOGIN UNENCRYPTED PASSWORD 'MY_PASSWORD' SUPERUSER INHERIT NOCREATEDB NOCREATEROLE NOREPLICATION;"
sudo -u postgres /usr/bin/createdb --echo --owner=MY_USER MY_DB_NAME
service postgresql restart
```

## License

MIT

## Credit

Josh Frye @joshfng on GitHub and Twitter
