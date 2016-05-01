# Rails Box

Vagrant box provisioned with Ansible to run Ruby on Rails applications. You can skip using this repo (and ansible run time) by using the prebuilt [Vagrant box](https://atlas.hashicorp.com/joshfng/boxes/railsbox/) `vagrant init joshfng/railsbox; vagrant up --provider virtualbox`

Includes:
 - Ubuntu 14.04 LTS
 - Latest stable Ruby (via rbenv)
 - Most current version of Bundler & Rails at time of `vagrant up`
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

For existing Rails projects copy the `Vagrantfile` and `ansible` directory to your Rails project directory and run:

```
$ vagrant up
$ vagrant ssh
$ cd /vagrant
$ bundle install
$ rails s -b 0.0.0.0
```

## Configuration

Locate the `vars:` section inside `ansible/main.yml` to change which version of Ruby you would like installed. You can also toggle on/off different databases using the `install_mysql`, `install_sqlite`, etc variables.

Edit `ansible/files/gemrc` to change default gem install options

Edit `Vagrantfile` to change CPU and Memory settings.

## License

MIT

## Credit

Josh Frye @joshfng on GitHub and Twitter
