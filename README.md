# PulsePlay

Draw signals. Play with timing.

Interactive digital timing simulator with editable input and clock edges, delayed copies, Boolean logic, D/T/JK/SR flip-flops, measurements, annotations, and diagram/project exports.

## Publish on GitHub Pages

1. Create a repository named `pulseplay` (public repositories support Pages on GitHub Free).
2. Upload the contents of this folder to the repository root. `index.html` must be at the root, not inside another folder.
3. Open **Settings → Pages**.
4. Set **Source → Deploy from a branch**, choose **main** and **/(root)**, and save.
5. Wait for the Pages deployment to finish. GitHub displays the exact published URL on that page.

The usual project URL is `https://YOUR-USERNAME.github.io/pulseplay/`.

All CSS and JavaScript paths are relative, so this also works at a repository subpath. No build step or server is needed. The `.nojekyll` file disables Jekyll processing.

## Local preview

Run `python3 -m http.server 8000` in this folder, then open `http://localhost:8000`. Use an HTTP server because the application uses JavaScript modules.

## Tests

With Node.js installed, run `npm test` (no dependencies to install).

## Project storage and simulation

Projects save in each browser's local storage. Use JSON export/import to move projects between browsers or devices. GitHub Pages has its own storage origin, so projects from the previous hosted site should be exported there and imported here.

Simulation uses integer femtosecond ticks and event-based propagation. Flip-flops sample immediately before the clock edge. Setup/hold violations, metastability, unknown states, and external feedback loops are not modeled.
