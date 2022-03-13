# php-selenium-browserstack

## Prerequisites 
1. php and composer should be installed in your system
2. Go to the directory where you have your test scripts and run the command below:
```
  composer require php-webdriver/webdriver
```

## Steps to run test sessions
1. Install dependencies
```
  # If you don't already use Composer, you can download the composer.phar binary:
  curl -sS https://getcomposer.org/installer | php

  # Include the binding:
  php composer.phar require browserstack/local:dev-master

  # Install all the dependencies:
  php composer.phar install

  # Test the installation by running a simple test file, check out example.php in the main repository.
```
2. Configure test capabilities
(To run single test, navigate to ./scripts/single/php)

```php
$caps = array(
    'bstack:options' => array(
        "os" => "OS X",
        "osVersion" => "Sierra",
        "buildName" => "Final-Snippet-Test",
        "sessionName" => "Selenium-4 PHP snippet test",
        "local" => "true",
        "seleniumVersion" => "4.0.0",
    ),
    "browserName" => "Chrome",
    "browserVersion" => "latest",
);
$web_driver = RemoteWebDriver::create("https://USERNAME:ACCESS_KEY@hub-cloud.browserstack.com/wd/hub",$caps);
```

3. Run tests
Single test
```
php single.php
```

Local test
Along with step-2 also use your Accesskey to bs_loca_args
```php
# In file ./scripts/local.php
# You can also set an environment variable - "BROWSERSTACK_ACCESS_KEY".
$bs_local_args = array("key" => "ACCESS_KEY");
```

```
php single.php
```
