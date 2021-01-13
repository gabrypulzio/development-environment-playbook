An Ansible playbook to configure a rails development machine in a Debian based distribution with:
- Asdf as a version manager
- Asdf plugins for ruby and nodejs
- Yarn
- Database development libraries for postgreSQL, MariaDB and SQLite

In addition:
- Configure a SSH key-based authentication
- Add the user to sudoers

It expects an inventory that defines "development" hosts (see inventory.example.yml)
You can execute the playbook with the command: `ansible-playbook develop_environment.yml -Kk -i inventory.yml`

If you don't want to install the database libraries you can skip them with `--skip-tags databases-lib`:
`ansible-playbook develop_environment.yml -Kk -i inventory.yml --skip-tags databases-lib`

After running the playbook you can install your favourites ruby and nodejs versions with asdf.

# Installing ruby and nodejs

1. Choose your ruby version from `asdf list all ruby`
2. Install ruby with `asdf install ruby [version]` e.g. `asdf install ruby 2.7.2`
3. Choose your nodejs version from `asdf list all nodejs`
4. Install nodejs with `asdf install nodejs [version]` e.g. `asdf install nodejs 15.5.1`
5. Set current version on your system according to the [asdf documentation](https://asdf-vm.com/#/core-manage-versions?id=set-current-version).
