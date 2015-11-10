# WP Objectly ACF
This is the ACF Extension for the [WP Objectly library](https://github.com/sigurdsvela/WP-Objectly). It provides function to the PostObject, PostTypeObject and PostObjectQueryBuilder class that is inherited. Meaning that these function will be provided to any sub class of these classes

All function are under the `->acf / ::acf()` namespace


# Quick Examples

## On a post object
```php

$post = Post::fromPostID(1);

// Set "fieldName" to "newValue"
$post->acf->updateField('fieldName', 'newValue');

// Will return "newValue"
$post->acf->getField('fieldName');
```

## On a post type

```php
// Get all field groups shown on this post type
PostType()->acf->getFieldGroups();

// Get all field shown for on this post type
PostType()->acf->getFields();
```

## With the query builder
```php
Post::get()
    ->fromAuthor(User::fromUserID(1))
    ->acf->withField('field', 'value')
    ->run();
```