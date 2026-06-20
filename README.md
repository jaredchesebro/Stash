# stash

Stash lets you save text and code snippets for reuse throughout your ExpressionEngine
templates — with variables, lists, partials, layouts/inheritance, parse-order control,
and full-page/fragment caching.

**Compatibility:** ExpressionEngine 7.5+ · PHP 8.3+

## Installation

1. Copy the `stash/` directory into your EE installation's add-ons directory:

   ```
   system/user/addons/stash/
   ```

2. In the EE control panel, go to **Settings → Add-Ons**.

3. Find **Stash** in the list and click **Install**. This installs both the module and the
   extension (the extension is required — it lets Stash control template parse order).

Stash is now ready to use in your templates. See the
[documentation](http://github.com/croxton/Stash/) for available tags.

### Updating

Replace the contents of `system/user/addons/stash/` with the new version. EE detects the
new version number and shows an **Update** prompt under **Settings → Add-Ons** — click it
to run any required database migrations.

## Testing

Add `stash.group` to `system/user/templates`.

Add to `config.php`:
```php
// Stash embed/template file settings (added for addon testing)
$config['stash_file_basepath'] = SYSPATH . 'user/templates/stash/';
$config['stash_file_sync'] = true; // always re-read embed files from disk (handy while developing)
```

Add to `system/user/templates/stash/card.html`:
```
<div class="card">
	<h3>{stash:title}</h3>
	<p>{stash:body}</p>
	<small>rendered by stash embed file card.html</small>
</div>

```
