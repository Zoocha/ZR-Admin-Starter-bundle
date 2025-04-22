# ZR Admin Theme Recipe Installation Guide

To install the ZR Admin Theme recipe, follow the steps below:

1. Ensure the below has been added to the `composer.json` **installer-paths**:
    ```sh
    "web/recipes/custom/{$name}": ["type:drupal-recipe"]
    ```
2. Run the following command (within the `/web` directory):

    ```sh
    ddev drush recipe recipes/custom/zr-admin-theme-starter-recipe
    ```

The above command will execute the ZR Admin Theme recipe installation and install the necessary modules.

Additionally, add the environment indicator settings in `settings.php` based on the environment:

```php
$config['environment_indicator.indicator']['name'] = 'Dev';
$config['environment_indicator.indicator']['bg_color'] = '#d8d887';

$config['environment_indicator.indicator']['name'] = 'Stage';
$config['environment_indicator.indicator']['bg_color'] = '#6eb6cb';

$config['environment_indicator.indicator']['name'] = 'Live';
$config['environment_indicator.indicator']['bg_color'] = '#e45656';
```

To ensure the environment indicator looks consistent, add the following CSS to your theme's custom CSS file:

```css
#toolbar-item-environment-indicator {
    border-radius: var(--gin-border-s) !important;
    color: #ffffff !important;
}
.gin-secondary-toolbar .toolbar-secondary .toolbar-bar .toolbar-tab #toolbar-item-environment-indicator.toolbar-item::before {
    background-color: #ffffff !important;
}
#toolbar-item-environment-indicator-tray {
    display: none !important;
}
#toolbar-item-administration-tray .toolbar-logo img {
    border-radius: 5px;
}
```

![ZR Environment Indicator CSS](./images/environment-indicator.png)
