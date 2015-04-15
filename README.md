# PimGento

PimGento is a Magento extension that allows you to import your catalog from Akeneo CSV files into Magento.

## How it works

Pimgento reads CSV files from Akeneo and insert data directly in Magento database.
In this way, it makes imports very fast and doesn't disturb your e-commerce website.
With PimGento, you can import these informations :
* Categories
* Families
* Attributes
* Options
* Products
* Products positions by category
* Images
* Stocks

## Features

* Plug and Play: We payed attention to the code and followed the Magento code instructions so you can easily install this extension on your store without any troubleshooting (see [installation](#installation)).
* Totally flexible: We added plenty of configurations. We didn't write any specific value in our code : No hard coding.
* User Friendly: We thought the interface the easiest possible. We developed a dashboard where you can see your import running. We even added some colors :)
* Manual or automatic: Free to choose ! You can either upload and import your CSV files from the Magento back-office or simply let the automatics tasks run different import with CSV files located in a directory of your server.
* SEO ready: 404 pages, it's over ! With PimGento, you don't loose SEO on your product and category pages. If their names change, Pimgento create automatically a rewrite from the old URL to the new one.
* Synchrone / Asynchrone: You can import right now your data in order to show them on the front-office or schedule a task in the coming days. Very usefull to prepare a marketing operation for instance.
* Fast import: PimGento is from 10 to 20 times faster than API and native Magento import/export system.
* Performance: Imports with PimGento don't slow down the store. Besides, you can select which cache you want to clear at the end of your import.
* Multi-X: PimGento supports all types of Magento structure. If you have multi-website and multi-store with lot of differents languages, imports will still work well.

## Requirements

* Magento >= 1.9 CE
* Magento >= 1.14 EE
* Set local_infile mysql variable to TRUE
* Flash Player

Adaptations for other Magento versions are in development (see [roadmap](#roadmap))

## Installation

* Copy the folder app/code/community/Pimgento and paste it in the folder app/code/community
* Copy the folder app/design/adminhtml/default/default/template/pimgento and paste it in the folder app/design/adminhtml/default/default/template
* Copy the file app/design/adminhtml/default/default/layout/pimgento.xml and paste it in the folder app/design/adminhtml/default/default/layout
* Copier the file app/etc/modules/Pimgento_All.xml and paste it in the folder app/etc/modules
* Copy the folder skin/adminhtml/default/default/pimgento and paste it in the folder skin/adminhtml/default/default
* Clear the cache (System > Cache Management)
* Disconnect / reconnect to the Back Office
* Refresh Magento compilation (System > Tools > Compilation)

## Configuration and Usage

* Configure store language and currency before import
* After category import, set the "Root Category" for store in "System > Manage Store"
* After attributes import, set attributes used to create configurable products

All PimGento configurations can be found in the Magento back-office at this path:
System > Configuration > Catalog > Pimgento

* General
  * Enable Log: if set Yes, write everything happens during the import in a file.
  * Log file: Log file name in var/log directory.
  * CSV line ending: Choose the character used to make a carriage return.
  * CSV delimiter: Choose the delimiter of your CSV files.
  * Admin language: Default language for admin values (products, categories, attributes, options). Example: en_US, de_DE, fr_FR...
  * Add website mapping: Match Magento website with PIM channel

* Categories
  * Enable Cron: if set Yes, you can enable the automatic import.
    * CRON expression: Configure when the automatic import will execute.
    * File: The filename of the CSV file used for the automatic import.
  * Clear cache: Choose which cache you want to clear after the import.
  * PIM code exclusion: PIM codes not to add in Magento, comma separated. Example: CAT01,CAT18,CAT56
  * Category depth: Choose the depth of your e-commerce navigation.
  * Is anchor: If set yes, all categories will be created as an anchor category.
  * Update url key: If set yes, it will create automatically an URL rewrite if the category name changed.

* Families
  * Enable Cron: if set Yes, you can enable the automatic import.
    * CRON expression: Configure when the automatic import will execute.
    * File: The filename of the CSV file used for the automatic import.
  * Clear cache: Choose which cache you want to clear after the import.
  * PIM code exclusion: PIM codes not to add in Magento, comma separated. Example: FAM01,FAM18,FAM56

* Attributes
  * Enable Cron: if set Yes, you can enable the automatic import.
    * CRON expression: Configure when the automatic import will execute.
    * File: The filename of the CSV file used for the automatic import.
  * Clear cache: Choose which cache you want to clear after the import.
  * PIM code exclusion: PIM codes not to add in Magento, comma separated. Example: ATT01,ATT18,ATT56
  * Specific types: You can make a mapping between PIM and MAGENTO attributes types.

* Options
  * Enable Cron: if set Yes, you can enable the automatic import.
    * CRON expression: Configure when the automatic import will execute.
    * File: The filename of the CSV file used for the automatic import.
  * Clear cache: Choose which cache you want to clear after the import.
  * PIM code exclusion: PIM codes not to add in Magento, comma separated. Example: OPT01,OPT18,OPT56

* Products
  * Enable Cron: if set Yes, you can enable the automatic import.
    * CRON expression: Configure when the automatic import will execute.
    * File: The filename of the CSV file used for the automatic import.
  * Clear cache: Choose which cache you want to clear after the import.
  * PIM code exclusion: PIM codes not to add in Magento, comma separated. Example: SKU01,SKU18,SKU56
  * Match attributes: You can make a mapping between PIM and MAGENTO attributes for simple product.
  * Default tax class: Choose the default tax class for each product imported.
  * Create Configurable: If set yes, it will create configurable product from the simple product data.
    * Configurable attributes: attributes to use for create configurable products
    * Configurable values: You can make a mapping between PIM and MAGENTO attributes for configurable product.

* Images
  * Enable Cron: if set Yes, you can enable the automatic import.
    * CRON expression: Configure when the automatic import will execute.
    * File: The filename of the CSV file used for the automatic import.
  * Delete image: If set Yes, delete all images used for the import.
  
* Stock
  * Enable Cron: if set Yes, you can enable the automatic import.
    * CRON expression: Configure when the automatic import will execute.
    * File: The filename of the CSV file used for the automatic import.

* Product position
  * Enable Cron: if set Yes, you can enable the automatic import.
    * CRON expression: Configure when the automatic import will execute.
    * File: The filename of the CSV file used for the automatic import.

**NB**: PimGento use Magento cronjob so you have nothing to add in your crontab.

## Roadmap

* Compatibility with Magento >= 1.6 CE
* Compatibility with Magento >= 1.10 EE
* Create this type of product : Bundle, packed, virtual and downloadable products.
* Think about a way to delete data
