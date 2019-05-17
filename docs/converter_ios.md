# Create iOS Application
  * Download `fase_ios` repository from [here](https://github.com/igushev/fase_ios);
  * Launch XCode;
  * Click on *Fase_iOS*;
  * Change *Display Name* to *Converter* (see picture below);
  * Change *Bundle Identifier* to *converter-fase* (see picture below);
  * As *Team* choose your account (see picture below);
<img alt='XCode Names' src='../images/converter_ios/xcode_names.png'>
  * Go to *Fase_iOS/API Client/APIClient.swift*;
  * Update `BaseURL.prod` to URL of deployed server
  `http://converterfase-env-prod.us-west-2.elasticbeanstalk.com/`;
  * Go to *Fase_iOS/AppDelegate.swift*;
  * Update Google API key if your Application uses signing up with home city selection and/or Place picker;
  * Uncomment line `NotificationService.instance.registerForRemoteNotifications()` if your Application uses
  push notifications;
  * Click on *Fase_iOS*. In *App Icons Source* add icons;
  * Set *Fase_iOS* as active scheme, click *Build and Run*;
  
If you have a connected iPhone, Application should run:
<img alt='Converter iOS Launch' src='../images/converter_ios/converter_ios_launch.png'>
  
  