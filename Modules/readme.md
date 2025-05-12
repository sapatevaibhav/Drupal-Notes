### Modules development
There are 4 modules:
- Hooks : ✅ Best for: Altering forms, content, menus, and other predefined areas.
- Plugins (OOP-based): ✅ Best for: Blocks, field types, views handlers, authentication, etc.
- Services (Dependency Injection): ✅ Best for: Database queries, API calls, caching, and reusability.
- Events (Observer Pattern): ✅ Best for: Logging, notifications, and reacting to Drupal system events.

| Feature |	Use Case |
|---------|----------|
| Hooks |	Simple procedural modifications (alter forms, menus, nodes). |
| Plugins |	When you need swappable and extendable components (blocks, field types). |
| Services |	When you need reusable logic with dependency injection (database, API calls). |
| Events |	When you need to listen for system-wide actions (user login, node creation). |


### info.yml file

1. **Some key points about the info.yml file:**

 - name: Details name of project
 - type: distinguishes project as module or theme
 - description: Provides a brief description of the project.
 - core_version_requirement: Indicates which Drupal core versions the module is compatible with.


2. **Some additional keys**

 - dependencies: List of needed modules
 - configure: Used if module has configuration form
 - php: Minimum PHP version required
 - hidden: Used if module is hidden from the list of available modules (Extend page)
 - required: Used if module is required for the site to function properly


### Types of Hooks
Action Hooks: Respond to drupal event (cron)
Alter Hooks: Modify existing data or behavior
Information Hooks: Provide additional information about the module

### Implementing hook

We are going to create a hook which displays custom message when we run cron job.

```php
function my_cron() {
   \Drupal::messenger()->addMessage(t('Hellowwwwwwwwwwwww')); # Displays message on UI
   \Drupal::logger('my')->notice('Hellowwwwwwwwwwwww'); # Displays message in logs
}
```

### Controllers and routing

Controllers are responsible for handling HTTP requests and returning responses. They are typically used to implement RESTful APIs or to handle user interactions.

Routing is the process of mapping URLs to controllers. Drupal uses the Symfony Routing component to handle routing.

To create the controller create a new file in the src/Controller directory with a name that follows the pattern [ControllerName]Controller.php. For example, if you want to create a controller for a blog post, you could create a file named BlogPostController.php.

inside it write the following code:

```php

namespace Drupal\my\Controller;

use Drupal\Core\Controller\ControllerBase;

class FirstController extends ControllerBase {
    public function index() {
        return [
            '#markup' => $this->t('Hello World'),
        ];
    }
}
```


### Connecting the database

There are 3 ways in Drupal to connect the database.

First way:
$database = \Drupal::database();

Second way:
$database = \Drupal::service('database');

Third way:
use \Drupal\Core\Database\Database;
$database = Database::getConnection();
