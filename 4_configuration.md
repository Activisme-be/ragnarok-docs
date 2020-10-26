# Configuration

The boilerplate comes with a custom configuration file that u can find under the following 
file name `<project directory>/config/spoon.php`. With this documentation file we will try 
to guide u trough the configuration so easy as possible. 

**Info:** All the configuration sections are also documented with a corresponding 
docblock for your ease.

### `spoon.kiosk_prefix`

Because not every application or developer wants to have the same management kiosk prefix. 
We decided to set it to a config variable, so you can easily modify the prefix of 
your management kiosk. Default is the kiosk prefix set to 'kiosk'. This prefix is also the route 
as the name prefix.

### Authentication configuration

In the authentication configuration section of the configuration you can easily configure the 
default password length for now. The default password length will be used when there is created 
a new user in the management kiosk. The default length is 12 characters

### Access configuration 

In the boilerplate we work with user groups that are stored in the GroupEnum and attached to the
users with a database relations. For now, we have two configs here. `superAdmin` and `kiosk`,

- **superAdmin:** 