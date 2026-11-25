# Changelog

## Unreleased

### Development

- CI installs `tzdata-legacy` on the Ubuntu runner. Ubuntu ships legacy timezone IDs such as `CET` only in that package, and without it PHP rejects `date_default_timezone_set('CET')`, which the tests use. Applications on such systems that pass legacy IDs to `Zend_Date` need the package too, or should use IDs such as `Europe/Berlin`.

## 2.0.0

Fork of `diablomedia/zendframework1-date`, published as `gizmocraft/zendframework1-date`.

### Breaking changes

- Requires PHP `>=8.5`. Tested on PHP 8.5 and 8.6.
- Package renamed from `diablomedia/zendframework1-date` to `gizmocraft/zendframework1-date`. It now requires `gizmocraft/zendframework1-exception`, `-cache`, `-loader` and `-locale`, all `^2.0.0`.

### Other changes

- No public signature changes and no library code changes: `src/` has no PHP 8.5 or 8.6 deprecations.
- Dev dependencies upgraded (PHPUnit 13, PHPStan 2.3, php-cs-fixer 3.95, GrumPHP 2.27). Dropped `composer-require-checker`, which has no release for PHP 8.6.
- Tests migrated to PHPUnit 13 attributes. CI runs PHP 8.5 and 8.6.
