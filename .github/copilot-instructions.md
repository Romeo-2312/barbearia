# Copilot / AI Agent Instructions for Barbearia Prime

Purpose: Help AI coding agents become productive quickly in this small static website repository.

Big picture
- This is a single-page static site (HTML+CSS+vanilla JS). Primary artifact: `index.html`.
- No build tools, package managers, or backend services found. Changes are served by opening `index.html` in a browser or running a simple HTTP server.

Key files to inspect
- `index.html` — entire UI, styles (inline `<style>`), and small JS live in this file. Example patterns: service cards use `onclick="showAlert('...')"` and CTA links to WhatsApp.
- `README.md` — repository description and link to GitHub pages (minimal).

Developer workflows (how to run/debug)
- View locally: open `index.html` in a browser or run a lightweight HTTP server (recommended) such as:
  - `python -m http.server 8000` (then open http://localhost:8000)
  - Use VS Code Live Server extension for hot reload.
- Debugging: use browser devtools (Elements, Console, Network). JS is inline — console errors point to `index.html` lines.

Project-specific patterns & conventions
- Language: UI text is Portuguese (`lang="pt-BR"`). Keep translations or UI copy changes in Portuguese unless instructed otherwise.
- Styling: currently implemented as inline `<style>` in `index.html`. If extracting to `styles.css`, update the `<link>` reference and preserve specificity and rules order.
- Scripts: small inline script at bottom (`showAlert(servico)`). When adding JS files, place them before `</body>` and keep functions unobtrusive (avoid changing inline `onclick` unless migrating consistently).
- External deps: Google Fonts and Font Awesome are loaded via CDN; do not remove without replacing.

Common edits and where to do them (examples)
- Update WhatsApp number in CTA: edit the `href` on the CTA button in `index.html` (search for `wa.me`).
- Add/remove services: edit the `.services` block (cards). Example card uses `class="card" onclick="showAlert('Corte Tradicional')"` with icon classes like `fas fa-scissors`.

Safety & localization notes
- Keep currency formatting for prices in `R$` if editing text content (e.g., `R$ 40`).
- Preserve `meta` viewport and charset lines in `<head>`.

When opening pull requests
- Keep changes small and focused (this is a tiny UI repo). If you move inline CSS/JS to separate files, include a short note explaining the reason and update the README with run instructions.

What not to assume
- There is no backend API or database; do not scaffold server-side code unless the user requests it.

If something is unclear
- Ask: "Should UI copy remain in Portuguese?" or "Do you want CSS/JS extracted to separate files?"

End of file.
