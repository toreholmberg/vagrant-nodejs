# Vagrant Node.js

Simple Vagrant VM for Node.js/MongoDB development.

## Prerequisites

* [Virtualbox](https://www.virtualbox.org/)
* [Vagrant](http://vagrantup.com/)

## Synced folders

Place app files in the `app` folder. This folder will be mounted as `/home/vagrant/app` in the VM.

Synced folders are mounted using NFS for better performance. Please see the Vagrant documentation for more information and prerequisites:

[http://docs.vagrantup.com/v2/synced-folders/nfs.html](http://docs.vagrantup.com/v2/synced-folders/nfs.html)


## Installation

1. Install [Chef](https://github.com/opscode/chef):

	````$ gem install chef````
	
2. Install [Librarian-Chef](https://github.com/applicationsonline/librarian-chef):

	````$ gem install librarian-chef````
	
3. Install cookbooks:

	````$ librarian-chef install````

4. Build Vagrant VM:

	````$ vagrant up````


## Usage

* Login to VM:
	
	````$ vagrant ssh````
	
* Suspend VM:

	````$ vagrant suspend````
	
* Resume VM:

	````$ vagrant up````

Vagrant documentation: [http://docs.vagrantup.com/v2/](http://docs.vagrantup.com/v2/).

