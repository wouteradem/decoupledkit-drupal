# Decoupled Drupal Kit

This repository contains a Decoupled Drupal instance using the Headless Lightning sub-profile. This project is intended as a central data source for various decoupled applications to illustrate typical workflows. This repository is intended to supply content via an API to its sibling application. The sibling application is located at [https://github.com/acquia-pso/decoupledkit-react](https://github.com/acquia-pso/decoupledkit-react).


### Overview

This project is based on BLT, an open-source project template and tool that enables building, testing, and deploying Drupal installations following Acquia Professional Services best practices.

To set up your local environment and begin developing for this project, refer to the [BLT onboarding documentation](http://blt.readthedocs.io/en/latest/readme/onboarding/). 

* Primary development branch: develop
* Local environment: DrupalVM
* Local drush alias: @decoupledkit.local
* Local site URL: http://local.decoupledkit.com

### Installation & Configuration Steps

These are the summarized steps which you can follow in the [BLT documentation](http://blt.readthedocs.io/en/latest/readme/onboarding/)

* Fork the develop branch and download locally with `git clone {your-forked-repo}`
* Navigate to the project root and install composer dependencies with `composer install`
* Install blt alias: `composer run-script blt-alias`
* Start your virtual machine: `blt vm`
* Build and install the Drupal installation: `blt setup`
* You should now see a local instance running at `http://local.decoupledkit.com`
* You can now login with `drush uli --uri=local.decoupledkit.com` *or* ssh into the vagrant box with `vagrant ssh` then navigate with `cd docroot/` and use `drush uli`
* The database and files directory can now be imported and added after downloading from [here](https://drive.google.com/drive/u/0/folders/1GCaCBYrC1LPVKyVUiTBfbmeDoVSPjvaG). 

*Additional Notes*

* PHP 7.1 is recommended locally, so you may need to update the `php_version ` in `box/config.yml` and re-provision your Drupal VM.


### Architectural Overview

#### Content Types

**Dogs** - content type and sample data to illustrate typical workflows with React CRUD operations as illustrated [here](https://screencast.com/t/vmGeHg3r). 

**Pokemon**	- content type and sample data for various characters from the Pokemon series to illustrate leveraging a GraphQL layer when using JSON API data as shown [here](https://screencast.com/t/NMxnOQ3qg).

**Marvel Characters** - content type and sample data for various characters from the Marvel universe, which is intended to be used in combination with external API sources as shown [here](https://screencast.com/t/uSX8yAvIbA).

**Client** - content type and sample data for client user data for the purposing of illustrating mocking local development APIs, along with caching options within React as illustrated [here](https://screencast.com/t/AGhDibb1). 

### Drupal Configuration

All configuration for Drupal is included with the [sample database](https://drive.google.com/drive/u/0/folders/1GCaCBYrC1LPVKyVUiTBfbmeDoVSPjvaG), but you can review or update the settings [http://local.decoupledkit.com/admin/access/users](http://local.decoupledkit.com/admin/access/users). The headers used in the React/GraphQL application are using the Drupal account `apitest` and you can review those permission settings [here](http://local.decoupledkit.com/admin/config/services/consumer).