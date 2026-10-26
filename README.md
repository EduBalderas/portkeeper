# portkeeper

## META
- id: portkeeper
- owner: EduBalderas
- visibility: public
- idioma: mixto
- estado: estable
- tipo: fork
- nivel: L3
  - L0=gobernanza/política
  - L1=marca/metodología
  - L2=flujo/arquitectura
  - L3=producto ejecutable
  - L4=herramienta
- familia: ninguna
- origen: upstream:https://github.com/MarcAparisiTFG/portkeeper
- experimento: desconocido
- nacido_de: MarcAparisiTFG/portkeeper
- orquestado_por: N/A
- brief_desde: N/A

## OBJETIVO
Widget de escritorio (Tauri 2, v0.5.0) que lista los puertos TCP en escucha y los contenedores Docker locales, muestra qué agente o IDE los arrancó, y permite abrirlos, pararlos o volver a lanzarlos.

## QUE_CONTIENE
- `src-tauri/`: backend Rust (`ports.rs`, `docker.rs`, `probe.rs`, `launch.rs`, `settings.rs`, `placement.rs`, `system.rs`, `lib.rs`); `Cargo.toml` versión 0.5.0, licencia MIT, autor Marc Aparisi Rull.
- `src/`: interfaz HTML, CSS y JS sin bundler (`index.html`, `main.js`, `style.css`, `i18n.js`, `mock.js`, `icons/`).
- `site/`: página de una sola vista e instaladores `install.sh` e `install.ps1`; homepage del repo `https://portkeeper.pages.dev`.
- `assets/`: icono, badges de descarga y script de capturas; `docs/`: capturas del widget.
- `.github/workflows/ci.yml` y `release.yml`; `package.json` (pnpm 11.28.6, scripts `tauri` `dev` y `build`).
- `CHANGELOG.md` (Keep a Changelog; release 0.5.0 el 2026-10-16), `CONTRIBUTING.md`, `LICENSE` (MIT, copyright 2026 Marc Aparisi Rull).

## CARACTERISTICAS
- Agrupa procesos por directorio de trabajo y los combina con el proyecto Docker Compose de esa carpeta. Docker se consulta con el CLI (`Docker Desktop`, Colima, OrbStack o el shim de Podman, según `docker.rs`).
- Identifica el agente o IDE subiendo el árbol de procesos: Claude Code, Claude, Codex, Cursor, Gemini CLI, Copilot, Windsurf, Aider, OpenCode, Cline, VS Code, Zed, JetBrains y Xcode (`ports.rs`).
- La UI asigna icono al runtime que sirve el puerto: Docker, Node, Vite, Next, Astro, Nuxt, Python, Ollama, Postgres, MySQL, Redis y otros listados en `src/main.js`.
- Sonda si el puerto responde; parar, bloquear y relanzar desde la lista Closed; enmascara secretos en la línea de comandos antes de guardarla.
- Ajustes: apariencia, idiomas en/es/fr/de/pt, arranque al iniciar sesión y búsqueda de actualizaciones. El updater apunta a `https://github.com/MarcAparisiTFG/portkeeper/releases/latest/download/latest.json`.
- `portkeeper --dump` imprime el escaneo en JSON y sale.
- Empaquetado y código contemplan macOS, Windows y Linux (AppImage en el README de upstream; `placement.rs` y `system.rs` tienen ramas Linux).
- Documentación, changelog y comentarios del código están en inglés; la interfaz incluye cadenas en inglés, español, francés, alemán y portugués. La descripción de este fork en GitHub está en español.

## FUERA_DE_ALCANCE
- Un gestor completo de contenedores: `CONTRIBUTING.md` lo deja fuera y limita el producto a puertos en escucha, contenedores y acciones rápidas.
- Abrir en el navegador otra URL que no sea `http://localhost:<port>`, o señalar un proceso que no esté en el último escaneo (`CHANGELOG.md`, 0.5.0).
- Certificado de desarrollador de Apple o Microsoft: el README de upstream dice que las builds aún no están notarizadas.
- Commits propios de EduBalderas: este fork no añade ninguno; `HEAD` es `d82f80d` (merge de la release 0.5.0 del upstream).

## RELACIONES
- Upstream (parent del fork): https://github.com/MarcAparisiTFG/portkeeper
- Release upstream v0.5.0: https://github.com/MarcAparisiTFG/portkeeper/releases/tag/v0.5.0
- Homepage: https://portkeeper.pages.dev
- Revisión de `main` y CODEOWNERS: @MarcAparisiTFG
- Topics de GitHub en el upstream (este fork tiene la lista vacía): ai-agents, developer-tools, docker, macos, menubar, ports, rust, tauri, tray, windows
- Referencias en el repo a sdf, agentability o gentle-ai: ninguna

## ETIQUETAS
- fork
- tauri
- rust
- desktop
- docker
- puertos
- mit

## TOPICS_GITHUB
- N/A
