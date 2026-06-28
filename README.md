# Leasum — Email templates

Transactional email templates for Leasum, built with [Maizzle](https://maizzle.com)
(Tailwind CSS for email). The built HTML is pasted into **Mailgun stored templates**,
which the API references by name when sending (see `api/Services/EmailService.cs`).

## Develop

```bash
pnpm install
pnpm dev      # live preview at the printed localhost URL
pnpm build    # outputs HTML to dist/
```

Templates live in `emails/*.vue`. Static assets (logos, etc.) go in `public/`.

## Mailgun variables

Mailgun fills `{{ token }}` placeholders at send time (Handlebars). Maizzle renders
each template with Vue, whose own `{{ }}` interpolation would otherwise consume those
tokens — so we declare each token as a JS string in `<script setup>` and interpolate
it, which emits the literal `{{ token }}` into the built HTML. Use `{{{ token }}}`
(triple braces) for values that contain HTML you don't want escaped (e.g. the body).

The API currently passes `recipientName` (see `EmailsService`); add more variables to
both the template's `<script setup>` and the API's variables map as needed.

## Publish to Mailgun

For now this is manual:

1. `pnpm build`
2. Open `dist/<template>.html`, copy its full contents.
3. In the Mailgun dashboard → **Sending → Templates**, create/update a template whose
   name matches the one in `EmailTemplateExtensions.ToMailgunTemplateName` (e.g. `letter`).
4. Paste the HTML and save.

## Templates

| File | Mailgun name | Purpose |
| --- | --- | --- |
| `emails/letter.vue` | `letter` | Generic branded letter — heading + free body, for sending clean ad-hoc emails to people. |
