# Lawanistreet

## Project Layout

- Entry pages stay at repository root (`*.html`).
- All static runtime files are under `assets/` (`css`, `js`, `img`, `fonts`, `video`, `favicons`, `slide`).
- Archived root-level legacy files are in `legacy/unused-root/`.

## File Management

```bash
./scripts/file-manager.sh status
./scripts/file-manager.sh largest
./scripts/file-manager.sh check-links
```

For a full-page/link validation run:

```bash
./scripts/file-manager.sh check-links all
```

See `docs/FILE_MANAGEMENT.md` for conventions.

## Contact Form

The live contact forms post to `php/mail.php` and deliver to `talktolawanistreet@gmail.com`. For production, deploy behind a PHP-capable server and configure:

- `CONTACT_FROM` (optional, falls back to the delivery address)
- `CONTACT_FROM_NAME` (optional)
- `SMTP_HOST`, `SMTP_USERNAME`, `SMTP_PASSWORD`, `SMTP_PORT`, `SMTP_ENCRYPTION` (optional SMTP delivery)

Without `SMTP_*`, the endpoint falls back to local `mail()`.
