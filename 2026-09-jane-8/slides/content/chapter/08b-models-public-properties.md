# Models: public, natively typed properties

## Generated models are plain PHP objects — getters & setters are gone

<div class="grid grid-cols-2 gap-8 text-sm mt-2">

<div>

### Before (7.x)

```php
$pet = new Pet();
$pet->setName('Rex');
$pet->getName(); // 'Rex'
```

</div>

<div>

### After (8.x)

```php
$pet = new Pet();
$pet->name = 'Rex';
$pet->name;      // 'Rex'

// uninitialized until assigned:
// reading before denormalization throws
```

</div>

</div>

<v-clicks>

- **Public, natively typed properties** replace getters & setters
- `$model->getFoo()` → `$model->foo` · `$model->setFoo($v)` → `$model->foo = $v`
- Plain PHP objects — IDE autocompletion, `clone`, `serialize` and reflection all work natively

</v-clicks>
