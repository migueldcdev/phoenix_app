# Phoenix setup

```shell
sudo apt update
sudo apt -qq install automake autoconf libreadline-dev libncurses-dev libssl-dev libyaml-dev libxslt-dev libffi-dev libtool unixodbc-dev build-essential libncurses5-dev libwxgtk3.0-gtk3-dev libgl1-mesa-dev libglu1-mesa-dev libpng-dev libssh-dev unixodbc-dev xsltproc fop dirmngr gpg

git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.15.0

. "$HOME/.asdf/asdf.sh"
. "$HOME/.asdf/completions/asdf.bash"

asdf plugin-add erlang
asdf plugin-add elixir
asdf install erlang 24.1.2
asdf global erlang 24.1.2
asdf install elixir 1.14.1-otp-24
asdf global elixir 1.14.1-otp-24
mix archive.install hex phx_new
sudo apt install postgresql postgresql-client
sudo su
sudo postgres
psql
CREATE DATABASE mydatabase;
CREATE USER myuser WITH PASSWORD 'mypassword';
GRANT ALL PRIVILEGES ON DATABASE mydatabase TO myuser;
```
Change config in app/config/dev.exs

config :app, App.Repo,
  username: "myuser",
  password: "mypassword",
  hostname: "localhost",
  database: "app_dev",
  stacktrace: true,
  show_sensitive_data_on_connection_error: true,
  pool_size: 10


```shell
sudo service postgresql start
mix phx.new app
cd app

```
