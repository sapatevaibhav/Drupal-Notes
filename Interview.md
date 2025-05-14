### What is Drupal
Drupal is a CMS framework which is free and open source written in PHP.

### Why is it powerful
Because we can create any content type withou knowing any programming with ease like article, blog, content type, etc.

### How caching works
Through caching drupal speeds up the websites
- Page caching - Entire HTML of each page will be cached
- Block caching - We can set cache for the views
there is lifetime for the cache to expire, On each cron run caches are cleared.
Cached pages are cleared on clearing the browser cache.

### PHP data object (PDO)
lean and consistant way to access databases. allows us to write portable code with ease.

### What is drush
Drush is a command line shell and UNIX scripting interface for Drupal.

### What is module in drupal
It is like a plugin for the Drupal site. It allows us to add different functions to our site

### SEO related modules
pathauto
Meta tags/ Node words
Service links
google analytics
related links
search 404
site Map
url list

### What is cron
to execute commands or scripts autometically at specified time and date intervals.

### Why drupal needs database
Drupal stores everything in the database like node, user, page, view and everything

### What is render arrays
Render arrays are the basic building blocks they provide a programmatical way to change the content befire it is being displayed.

### Required files for the module
- module.info.yml : Declares module in drupal
- module.routing.yml : OPTIONAL for defining path
- module.services.yml : OPTIONAL for defining services
- src/Controller/MyController.php : If routing is used handles the Route
- .module - for defining Hooks

### Required files for the theme
- theme.info,yml : Declares the theme
- theme.libraries.yml : Defines css and js assets used
- theme.theme : for implementing Hooks
- templates/*.html.twing : for definign different different templates
- css/* & js/* : OPTIONAL for styling and scripting

### Required files for the SDC (Single Directory Component)
- card.component.yml REQUIRED :  Describes the component and maps variables.
- card.twig REQUIRED : The template
- card.css (optional) : Scoped styles for the component.
- card.js (optional) : Scoped JavaScript for interactivity.
- card.php (optional) : Preprocessing logic for the component.

### What is the role of Composer in Drupal 11?
Composer is used to manage Drupal core, contributed modules, themes, and their PHP dependencies. It handles downloading, updating, and autoloading libraries.

### Explain the concept of "Configuration Synchronization".
Configuration Synchronization (Config Sync) is a system for moving configuration changes (like content types, views, fields) between different environments (e.g., dev, staging, prod) using YAML files.

### What is a Drupal Service?
A service is any object managed by the services container. Drupal uses services for global or reusable functionality, promoting loose coupling and testability through dependency injection.

### How does Drupal 11 handle dependency injection?
Drupal 11 uses a services container based on Symfony's Dependency Injection component. Services are defined in `*.services.yml` files and injected into classes via their constructors or setter methods.

### What is the Plugin System in Drupal?
The Plugin System allows a module or Drupal core to provide swappable pieces of functionality. Examples include blocks, field types, and views display extenders. Plugins are discovered and managed by plugin managers.

### What are Entities in Drupal?
Entities are any distinct piece of data in Drupal. Common examples include nodes (content), users, taxonomy terms, and comments. Custom entities can also be created.

### What is the Fields API?
The Fields API allows developers to attach different types of data (fields) to entities. This includes defining field types, formatters (how fields are displayed), and widgets (how field data is input on forms).

### What is the difference between a Content Entity and a Config Entity?
Content Entities represent user-generated content (e.g., nodes, users). Config Entities represent site configuration (e.g., content types, views, image styles).

### What is Twig and why does Drupal use it?
Twig is a flexible, fast, and secure template engine for PHP. Drupal uses Twig for its theme layer, separating presentation logic from business logic, and providing features like automatic output escaping for security.

### How can you pass variables from a preprocess function to a Twig template?
In a preprocess function (e.g., `MYTHEME_preprocess_node()`), you can add variables to the `$variables` array. These variables then become available in the corresponding Twig template.

### What is the purpose of `*.routing.yml` files?
`*.routing.yml` files define routes, which map URL paths to controller actions or other callbacks. They specify requirements, parameters, and access control for paths.

### What is a Controller in Drupal?
A controller is a PHP class method responsible for handling a request and returning a response, often HTML, JSON, or a redirect. They are defined in routing files.

### How does Drupal's Event System work?
Drupal's Event System, based on Symfony's EventDispatcher component, allows modules to react to or modify actions occurring within Drupal core or other modules by dispatching and subscribing to events.

### What is Headless or Decoupled Drupal?
Headless Drupal means using Drupal as a backend content repository, with the frontend (presentation layer) being handled by a separate application (e.g., a JavaScript framework like React, Vue, or Angular) that consumes Drupal's content via APIs.

### What are some key modules for building REST APIs in Drupal?
Core modules like JSON:API and RESTful Web Services are essential. JSON:API provides a feature-rich, specification-compliant API with minimal configuration.

### What is the role of the `*.info.yml` file for a module or theme?
The `*.info.yml` file provides metadata about a module or theme, such as its name, description, type, core version compatibility, and dependencies.

### What is the Drupal Cache API?
The Cache API provides a way to store and retrieve data that is expensive to compute, improving performance. It supports different cache backends, tags for invalidation, and contexts for variations.

### How can you clear Drupal's cache?
Caches can be cleared via the UI (Administration > Configuration > Development > Performance), using Drush (`drush cr` or `drush cache:rebuild`), or programmatically using the `\Drupal::cache()` service.

### What is the Project Browser initiative in Drupal?
Project Browser aims to make it easier for site builders to find and install contributed modules and themes directly from the Drupal admin UI, without needing Composer on the command line for basic sites.

### What are Automatic Updates in Drupal?
Automatic Updates is an initiative to provide a secure and reliable way for Drupal sites to automatically update to new minor and patch versions of Drupal core, improving security and maintenance.

### What is the significance of Symfony components in Drupal?
Drupal core incorporates many Symfony components (e.g., HttpFoundation, Routing, EventDispatcher, DependencyInjection, Console). This allows Drupal to leverage robust, well-tested, and widely adopted PHP libraries.

### How does Drupal 11 support PHP 8.1+ features?
Drupal 11 requires PHP 8.1 or higher, allowing developers to use modern PHP features like enums, readonly properties, fibers (for asynchronous programming potential), and improved type safety, leading to more robust and maintainable code.

### What is CKEditor 5 in Drupal 11?
CKEditor 5 is the default rich text editor in Drupal 11, replacing CKEditor 4. It offers a more modern UI, better collaboration features, and a more flexible architecture.

### How does Drupal address accessibility (A11Y)?
Drupal core is committed to meeting web accessibility standards (WCAG). This includes semantic HTML, ARIA attributes, keyboard navigability, and tools for content creators to make accessible content. The Claro admin theme is also designed with accessibility in mind.

### What is the Migration API in Drupal?
The Migration API is a powerful ETL (Extract, Transform, Load) framework within Drupal core used for migrating content and configuration into Drupal from older Drupal versions or external sources.
