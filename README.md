<img src="https://docksal.io/img/docksald.png" alt="Docksal.io" height="25"/> <img src="https://cdn4.aoe.com/fileadmin/AOE.com/images/logos/products/OROplatform_color.svg" alt="OroPlatform" height="90"/> <img src="https://www.orocommerce.com/wp-content/uploads/sites/3/2017/01/logo-orocommerce-e1440657988810.png" alt="OroCommerce" height="90"/> <img src="https://www.orocrm.com/wp-content/themes/orocrm/images/orocrm_logo.svg" alt="OroCRM" height="24"/>

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

When the automated install is complete the command line output will display the admin username and password.


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
