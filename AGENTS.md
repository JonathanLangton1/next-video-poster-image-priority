# next-video

## Package manager
This project uses bun to install packages and run scripts. TypeScript, esbuild and the Node test runner still run on Node.
- Install: `bun install` (CI and fresh checkouts: `bun install --frozen-lockfile`).
- Scripts: `bun run <script>`. Tests are `bun run test`, never plain `bun test` (that starts bun's own test runner, not Node's). One-off tools: `bunx <tool>`.
- Add or remove packages with `bun add` / `bun remove`, and commit `bun.lock`. Never use npm, npx or `package-lock.json`.
- Releases still publish to the npm registry: `wet-run` in the CD workflow calls `npm publish`. That's the registry, not the package manager.
