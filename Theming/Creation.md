# Creating a custom theme

### Setting up

To create a custom theme we need to follow the below process

1. In project directory create new folder under `web/themes/custom/` name it.
2. Under it **.info.yml** file is created such a way project detects the theme.
        The file contains

```yml
name: Simple college theme                          # Name of the theme
type: theme                                         # Type representing as theme
description: "A test theme for my college website"  # A simple description
core_version_requirement: ^9 || ^10 || ^11          # The version on drupal core required
core: ^10                                           # Best works on which drupal version
base theme: stark                                   # This theme depends on which theme
```

![alt text](image.png)

### Adding regions to block layout

now it is time to add the regions to the theme just like above create new pair like below
```yml
regions:
    NAME: VALUE
    NAME1: VALUE1
```
and so on.

Flush the cache and enable all the disabled blocks from the block layout menu.

Changes the regions accordingly to our website needs
![alt text](image-3.png)

---

Now our new regions are visible in the Block Layout menu.
![alt text](image-4.png)

Then I cloned a **./templates/page.html.twig** file from the inbuilt theme and made some changes to display our all regions defined in our **.info.yml** file.




<!--
### Adding libraries

1. Define asset library in <em>.libraries.yml</em>.
2. Declare assets into **.info.yml** using libraries key.
3. Reference as needed in *.css* and *.html.twig* files.
 -->
---

 ### Pipeline

![alt text](image-2.png)

---
### Overriding the settings

To override the default **settings.php** file from **web/sites/default/settings.php** we need to create the **settings.local.php** file in the same directory and load it at the very bottom of our main **settings.php** file such a way it takes full effect and nothing gets overriden by default settings.

```php
if (file_exists($app_root . '/' . $site_path . '/settings.local.php')) {
  include $app_root . '/' . $site_path . '/settings.local.php';
}
```

and from that local php settings file uncomment the **Disable the render cache.** and **Disable Dynamic Page Cache.** such a way page directly gets loaded from HTML twig files and not from the cache. <br>
In short there is no need to **Flush cache** every time we make changes to the codebase.


### Overriding services.yml

Similarly **web/sites/default/default.services.yml** file gets overriden by **web/sites/development.services.yml** so we can add properties to this file such a way defaults gets overriden.

added below lines

```yml
parameters:
  twig.config:
    debug: true # outputs some extram markup along with each twig template also we can use inspect option
    auto_reload: true
    cache: false
```


Render caching disabled and twig debug mode enabled.

At final rebuild the cache from now on there is no need of the same.






---

### Fields in the theme

Create **theme-settings.php** file in the **custom/simplecollege** folder.

Adds a section "Simple College Theme Settings" in the Appearance → Theme Settings page.
Creates:

    Checkbox for enabling a custom logo.
    Text field for a custom footer message.

Saves the settings when the form is submitted.

before it was like below having default fields for our custom theme.

![alt text](image-5.png)

and now we can see two new options are there which we have added to the php file.

![alt text](image-6.png)

We need hooks for the implementation of the same.
