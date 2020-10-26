# Service providers 

Service providers are classes that more or less 'start up' your project.
Laravel comes default with a couple service providers. And some service providers are added or modified 
for our needs in the Ragnarok boilerplate. In this document we document which one we have added or modified. 

## Default service providers that have changes. 

- AppServiceProvider 
- AuthServiceProvider 
- EventServiceProvider 
- RouteServiceProvider 

## Added service providers

- TelescopeServiceProvider 
- HelperServiceProvider 
- BladeComponentServiceProvider 
- AnnouncementServiceProvider

### Overview of the service providers 

### AppServiceProvider 

(todo description)

The following modifications are implemented into the AppServiceProvider: 

- Method for changing the default personal access token model from laravel/sanctum 
- Method for mapping spatie/flash functions to custom css classes. 
- Method for only registering the TelescopeServiceProvider only under development environment(s). 

### AuthServiceProvider 

The AuthServiceProvider is responsible for things like authorization policies that needs to registered for using 
some level of authorization on specific parts of the application. 

The following modifications are implemented into the AuthServiceProvider: 

- Mapped the User model to the UserPolicy class in the `$policies` array 
- Mapped the Role model to the RolePolicy class in the `$policies` array 
- Mapped the Announcement model to the AnnouncementPolicy class in the `$policies` array. 
- Implemented an `Gate::after()` check for the configurable super admins in the application.

### BladeComponentServiceProvider 

The blade service provider is responsible for registering blade components that are used throughout the boilerplate.
For more information on the blade components you can read trough the following, [documentation article]() that is
dedicated to the blade components we use.

### EventServiceProvider 

The EventServiceProvider is responsible for mapping event listeners or registering Class event listeners or other
events in the application. 

The following modifications or mappings are implemented into the EventServiceProvider 

- Added the UserEventListener class event subscriber. 
- Added the PersonalAccessTokenEventListener class event subscriber. 
- Added the RoleEventListener class event subscriber. 
- Added the AnnouncementListener class event subscriber. 

### HelperServiceProvider 

The HelperServiceProvider is a service provider we added into the boilerplate and is hereby responsible 
for registering all the default helpers into the boilerplate. 

For more information on the implemented helpers you can read trough the following [documentation article]() that is 
dedicated to the helpers. That we have implemented, or the creation process.


### RouteServiceProvider 

The RouteServiceProvider is a service provider that is responsible for registering things like the default "home" route
for the application, The controller namespace or things like model bindings, patterns filters, etc. The only thing we have 
added here is the trashedToken model binding for restoring a personal access token in the application. 

### TelescopeServiceProvider

The TelescopeServiceProvider is a default service provider for configuring the debugger for laravel applications. 
U can find more information on what u can do within the provider in their [official documentation](https://laravel.com/docs/8.x/telescope)

### AnnouncementServiceProvider 

The AnnouncementServiceProvider is a service provider that we've added into the boilerplate and is responsible for the needed 
view composers and counters that we use in the application layout. 
