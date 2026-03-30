## Steps to package a Next.js app with Tauri
1. Ensure Next.js app works
``bash
pnpm dev
``
2. Configure static export
next.config.js
``ts
output: "export"
``

3. Build:
``bash
pnpm build
``
4. Install Tauri CLI
``bash
pnpm add -D @tauri-apps/cli
``
5. Initialize Tauri
``bash
npx tauri init
``
6. Configure Tauri
Ensure:
src-tauri/tauri.conf.json

Set:
``json
{
  "build": {
    "distDir": "../out",
    "devUrl": "http://localhost:3000"
  }
}
``

7. Install Rust
``bash
curl https://sh.rustup.rs -sSf | sh
``
Verify:
``bash
rustc --version
cargo --version
``
8. Run in development
Start Next.js:
``bash
pnpm dev
``

Running the next dev server will automatically run the following:
``bash
npx tauri dev
Build desktop app
npx tauri build
``
