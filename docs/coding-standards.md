---
layout: page
title: Coding Standards
permalink: /coding-standards/
---

Write accurate [PHPDoc](http://en.wikipedia.org/wiki/PHPDoc) styled code comments.

Write real Classes or Namespaced functions.

[PHP Namespaces](https://secure.php.net/manual/en/language.namespaces.php) have been available since 2009. Namespaces are not a new concept. We use them.

Our namespace is: `\Pressbooks\`

 * If your Class isn't an Object like `\WP_User`, `\WP_Dependencies`, `\WP_Query` etc., write a library of functions.
 * If your Class is a bunch of Static methods and nothing else, write a library of functions.
 * Afraid of function name collisions? See [Namespaces](https://secure.php.net/manual/en/language.namespaces.php).

Functions are `written_like_this()`.
Class methods are `writtenLikeThis()`.

Rules of thumb:

 * `getFooBar()` is when you are getting something associated with an object -- it implies the set is already defined.
 * `loadFooBar()` is when you are loading from an external source, like a file or a database.
 * `isFooBar()` or `hasFooBar()` is when a method returns a boolean value.
 * `createFooBar()` is when a method creates new files or assets.

Don't write `public function foo()`, just write `function foo()`. Public is implied.
Order of methods in a class:

1. `magic`
2. `public`
3. `protected`
4. `private`
5. `static`

Prefix WP Post meta keys with `pb_`.
Prefix WP User meta keys with `pb_`.
Prefix WP Option names with `pressbooks_`.

Files under `themes-book/` and `themes-root/` are exempt from the above rules, but should still make an effort to follow them.

For everything else not mentioned we respect the [WordPress coding standards](http://make.wordpress.org/core/handbook/coding-standards/php/).

## Validating with PHP Code Sniffer

From the Pressbooks plugin directory:

1. `composer install --dev`
2. `composer standards`
