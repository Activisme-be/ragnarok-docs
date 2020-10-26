# Service layer 

Services are classes to attempt database logic out of the controllers. 

There is a BaseService class you can extend, whose constructor accepts a model and
inherits some useful functionality such as `->get();`, `->count();`, `->find();`, etc. 

**Example:** 

```php
// Instead of duplicate this line everywhere:
$user = User::findOrFail($identifier);

// You can use 
$user = resolve(UserService::class)->findOrFail($identifier);
```

It's longer, but it's extracted out to one place in the codebase instead of duplicating logic everywhere. 
This is just an example, and a one liner usually isn't a big deal, but extracting out multi-line logic that 
doesn't belong in a model or elsewhere is good to have in a service dedicated to one model.

See the [BaseService.php](https://github.com/Activisme-be/Ragnarok/blob/main/app/Support/Services/BaseService.php) file for more information.