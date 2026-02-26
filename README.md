# 🏞️ Inverness — Premium Filament Theme

A refined, premium theme for [Filament](https://filamentphp.com) with tight spacing, subtle shadows, and dynamic primary color accents. Designed for Filament v4 and v5.

---

## Features

- **Tight border-radius** — Clean 4px corners across all components
- **Dynamic primary color** — Automatically adapts to your panel's configured primary color
- **Refined shadows** — Subtle, layered box-shadows for light & dark modes
- **Compact spacing** — Denser tables, sections, sidebar, and form elements
- **Full dark mode** — Carefully tuned values for both light and dark themes
- **Smooth transitions** — Polished 100ms/180ms transitions on interactive elements
- **Active sidebar indicator** — Primary color accent bar on the active nav item
- **Stat widget hover effect** — Top-border reveal on hover
- **Zero dependencies** — Pure CSS, works with Tailwind v3 and v4

---

## Installation

### 1. Add the private repository

Add the Anystack repository to your `composer.json`:

```json
{
    "repositories": [
        {
            "type": "composer",
            "url": "https://theme-inverness.composer.sh"
        }
    ]
}
```

### 2. Install the package

```bash
composer require spykapps/theme-inverness
```

When prompted, enter your license credentials:

```
Authentication required (theme-inverness.composer.sh):
Username: [your-email]
Password: [your-license-key]
```

> If your license requires a fingerprint, append it to the license key separated by a colon:
> `your-license-key:your-fingerprint`

To store your credentials globally so you're not prompted every time:

```bash
composer config --global --auth http-basic.theme-inverness.composer.sh [your-email] [your-license-key]
```

### 3. Run the install command

```bash
php artisan inverness:install
```

This will automatically detect your Filament panel(s), create a theme stylesheet if needed, and add the Inverness import.

### 4. Register the plugin

Add the plugin to your panel provider:

```php
use SpyApp\ThemeInverness\ThemeInvernessPlugin;

public function panel(Panel $panel): Panel
{
    return $panel
        // ...
        ->plugin(ThemeInvernessPlugin::make());
}
```

### 5. Compile your assets

```bash
npm run build
```

---

## Customization

The theme automatically uses your panel's primary color. Just set it as you normally would in your panel provider:

```php
use Filament\Support\Colors\Color;

$panel->colors([
    'primary' => Color::Blue,
    // or any custom color
    'primary' => Color::hex('#6366f1'),
])
```

The theme will pick up the color and apply it to buttons, focus rings, active indicators, stat widget accents, and more.

---

## Requirements

- PHP 8.1+
- Filament v4 or v5
- A valid license from [Anystack](https://anystack.sh)

---

## Support

If you run into any issues, please reach out at [hello@spykapps.com](mailto:hello@spykapps.com).

---

<p align="center">
    Made with ❤️ by <a href="https://spykapps.com">Spykapps</a>
</p>
