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

For new projects, clone this repo into a directory you want to name your app and run:
```
# locally
$ git clone https://github.com/joshfng/railsbox.git blog
$ cd blog && rm -rf .git #removes the railsbox git info
$ vagrant up
$ vagrant ssh

# inside the vm
$ cd /vagrant
$ rails new . -d YOUR_DATABASE
$ rake db:create db:migrate
$ rails s -b 0.0.0.0
#-b 0.0.0.0 needed to access 3000 outside of vagrant
```

For existing Rails projects copy the `Vagrantfile` to your Rails project directory and run:

```
$ vagrant up
$ vagrant ssh
$ cd /vagrant
$ bundle install
$ rails s -b 0.0.0.0
```

## License

MIT

## Credit

Josh Frye @joshfng on GitHub and Twitter
