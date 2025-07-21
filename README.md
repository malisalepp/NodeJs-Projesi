# README content expressed as a single YAML file
name: "Node Webserver 🌐"

description: >
  A minimal Node.js project that serves a static website (HTML + CSS) from a
  **public** directory. Perfect as a starter template for small portfolios,
  landing pages, or course demos.

features:
  - "Tiny footprint – just Node.js and one small server file (`server.js`)"
  - "Zero build‑tools – pure HTML + CSS, no bundlers required"
  - "Auto‑restart ready – works great with `nodemon` for live‑reload during development"
  - "Easily extensible – drop any additional static assets into `public/`"

project_structure: |
  node-webserver/
  ├─ node_modules/          # installed dependencies (auto‑generated)
  ├─ public/                # static assets served by the server
  │  ├─ index.html
  │  ├─ about.html
  │  ├─ contact.html
  │  └─ style.css
  ├─ server.js              # ⇦ tiny Express/HTTP server
  ├─ package.json           # project metadata & scripts
  ├─ package-lock.json
  └─ README.md              # ← you are here

quick_start: |
  # 1. Install dependencies
  npm install

  # 2. Run the server
  npm start               # default: node server.js  (PORT=3000)

  # 3. Visit the site
  # open http://localhost:3000         (or whichever port you set)

development_mode: |
  # Hot‑reload with nodemon
  npm run dev             # requires nodemon – install once: npm i -D nodemon

  # Custom port
  PORT=5000 npm start

scripts:
  - script: "npm start"
    purpose: "Launch the server with Node"
  - script: "npm run dev"
    purpose: "Launch with **nodemon** for hot reload"

how_it_works: |
  // server.js (simplified)
  const express = require('express');
  const app     = express();
  const PORT    = process.env.PORT || 3000;

  // Serve everything inside /public as static files
  app.use(express.static('public'));

  app.listen(PORT, () =>
    console.log(`Server running → http://localhost:${PORT}`)
  );

customisation_tips:
  - task: "Change site title / content"
    where: "Edit the HTML files in `public/`"
  - task: "Update styling"
    where: "Tweak `style.css` – add media‑queries or CSS variables"
  - task: "Add JS interactivity"
    where: "Place JS files in `public/` and reference them in the HTML"
  - task: "Introduce templating / API"
    where: "Extend `server.js` with Express routes or a view engine"

contributing: |
  1. Fork the repo & create a branch (`git checkout -b feature/awesome`)
  2. Commit your changes (`git commit -m 'Add awesome feature'`)
  3. Push to the branch (`git push origin feature/awesome`)
  4. Open a Pull Request.
