# Repo-Ubuntu-20.04
How to Configure Repositories on Ubuntu 20.04

List of repositories in Ubuntu

To view all repositories in the system:

nano /etc/apt/sources.list

They can also be located in one of the files in the /etc/apt/sources.list.d/ folder.

To disable one of the repositories, just comment out its line.

# deb http://archive.ubuntu.com/ubuntu focal multiverse

Adding repositories in Ubuntu

To add a repository you need to find out its address from the software developer and use the apt-add-repository command with the following syntax:

apt-add-repository ‘deb http://repository_address version branch’

Sometimes you need to install the GPG security key first. Let's take MariaDB as an example.

apt-key adv --fetch-keys 'https://mariadb.org/mariadb_release_signing_key.asc'

Adding repository:

add-apt-repository 'deb [arch=amd64,arm64,ppc64el] http://mirror.mephi.ru/mariadb/repo/10.5/ubuntu focal main'

Removing repositories

To remove a repository use this command:

add-apt-repository --remove 'deb [arch=amd64,arm64,ppc64el] http://mirror.mephi.ru/mariadb/repo/10.5/ubuntu focal main'

PPA repository in Ubuntu

During the installation of the PPA repository, the system automatically recognizes the repository and downloads the necessary keys.

apt-add-repository ppa:repository/ppa

To remove PPA repository:

apt-add-repository --remove ppa:repository/ppa

After editing the list of repositories, don't forget to update the list of packages in the system.

apt update
