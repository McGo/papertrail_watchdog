# Papertrail watchdog

## Introduction

This is a drupal 7 module that forwards watchdog entries to [papertrail](papertrailapp.com) via UDP. This could be used as a replacement for the existing watchdog database logging module and could be used without having access to syslog configuration. If you have access to the syslog configuration of your drupal server, it would be better to let all/some syslog entries be forwarded to papertrail directly as described in [this knowledgebase article](http://help.papertrailapp.com/kb/configuration/configuring-remote-syslog-from-unixlinux-and-bsdos-x/) 

## Requirements

This module has no requirements.

## Installation

* Download the [zip file](https://github.com/McGo/papertrail_watchdog/archive/master.zip) from [this repository](https://github.com/McGo/papertrail_watchdog)
* Rename the folder papertrail_watchdog_master to papertrail_watchdog
* Copy the folder as usual to your sites/modules folder, see [this](https://drupal.org/documentation/install/modules-themes/modules-7) for further information.

## Configuration

* Setup a [papertrail](papertrailapp.com) Account and add a [log destination](https://papertrailapp.com/account/destinations) to accept udp packets
* Copy this snippet to your settings.php and adjust the values for your papertrail host and port.

```php
/**
 * Configure papertrail_watchdog module
 */
 
// Enable the papertrail module. This could be set to FALSE on dev instances.
$conf['papertrail_watchdog_enabled'] = TRUE;

// Set the papertrail host and port as setup on https://papertrailapp.com/account/destinations
$conf['papertrail_watchdog_host'] = ADD_YOUR_PAPERTRAIL_HOST;
$conf['papertrail_watchdog_port'] = ADD_YOUR_PAPERTRAIL_PORT;

// Add an identifier that will be used in papertrail to identify this drupal site.
$conf['papertrail_watchdog_identifier'] = YOUR_SITE_IDENTIFIER;

```
* Enable the module. 
* Feel free to disable the watchdog database logging or syslog modules. 

## Maintainers/Sponsors

Current maintainers:

* [Mirko Haaser](https://github.com/McGo)

## License

[GPLv3](http://www.gnu.org/licenses/gpl-3.0.txt)
