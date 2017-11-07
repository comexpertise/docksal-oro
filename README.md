![Docksal.io](https://img.shields.io/badge/Docksal-.io-blue.svg?style=flat-square) ![OroPlatform](https://img.shields.io/badge/Oro-Platform-green.svg?style=flat-square) ![OroCRM](https://img.shields.io/badge/Oro-CRM-green.svg?style=flat-square) ![OroCommerce](https://img.shields.io/badge/Oro-Commerce-green.svg?style=flat-square)

## Notes

__Currently, only [OroCRM](https://www.orocrm.com) application can be installed.__

#### TODO

* Add method for [OroCommerce](https://www.orocommerce.com) and [OroPlatform](https://www.orocrm.com/oro-platform) installations
* Choose version for install

# Docksal powered Oro Application Installation

This is a sample vanilla Oro application ([OroCRM](https://www.orocrm.com), [OroCommerce](https://www.orocommerce.com) or empty [OroPlatform](https://www.orocrm.com/oro-platform)) installation pre-configured for use with Docksal.  

Features:

- Oro application ready for bundles developments
- `fin init` [example](.docksal/commands/init)
- Using the [default](.docksal/docksal.env#L9) Docksal LAMP stack with [image version pinning](.docksal/docksal.env#L13-L15)
- PHP and MySQL settings overrides [examples](.docksal/etc)

## Setup instructions

### Step #1: Docksal environment setup

**This is a one time setup - skip this if you already have a working Docksal environment.**  

Follow [Docksal environment setup instructions](https://docs.docksal.io/en/master/getting-started/env-setup)

### Step #2: Project setup

1. Clone this repo into your Projects directory

    ```
    git clone https://github.com/comexpertise/docksal-oroplatform.git oro_myapp
    cd oro_myapp
    ```

2. Initialize the site

    This will initialize local settings and install the application

    ```
    fin init
    ```

3. Point your browser to

    ```
    http://oro-myapp.docksal/app_dev.php
    ```
    
    Login with login/password: __admin/admin__
    
4. Add your custom bundle to docroot/src directory. See [How to create new bundle](https://www.orocrm.com/documentation/2.0/cookbook/how-to-create-new-bundle)

## More automation with 'fin init'

Site provisioning can be automated using `fin init`, which calls the shell script in [.docksal/commands/init](.docksal/commands/init).  
This script is meant to be modified per project. The one in this repo will give you a good starting example.

Some common tasks that can be handled by the init script (an other [custom commands](https://docs.docksal.io/en/master/fin/custom-commands/)):

- initialize local settings files for Docker Compose, Behat, etc.
- import DB or perform a site install
- compile Sass
- enable/disable modules, update variables values

# Links:

Documentation:

* https://docs.docksal.io/en/master/
* https://www.orocrm.com/documentation/2.0/book/installation

Inspirations:

* https://github.com/docksal/drupal8
* https://github.com/djocker/orobase
