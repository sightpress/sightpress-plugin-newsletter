# SightPress newsletter manager

`sightpress/plugin-newsletter-manager`: the official SightPress plugin for email
newsletters. Licensed GPL-2.0-or-later.

> **Status:** M0 scaffolding in place (manifest, bundle, quality gates, CI);
> features arrive in milestone M12.

It adds:

- **Double opt-in subscriber lists** and an `::newsletter` sign-up block for any
  page or widget area.
- A **`newsletter_issue` content type**, written once and sent as accessible
  HTML plus a plain-text part, following the same editors and linter as every
  other content type.
- **One-click unsubscribe**, a public issue archive, and no tracking pixels or
  open/click tracking of any kind.

Sending always runs through background jobs, in batches, so a large list never
blocks the request or the admin.

## Development

```bash
composer install
vendor/bin/phpunit          # on PluginTestCase, enabled and disabled
vendor/bin/phpstan analyse
npx playwright test         # every manifest route, with axe-core
```

Check out `sightpress/core` as a sibling and require it with
`COMPOSER=composer.dev.json composer install` to run the test kernel.
