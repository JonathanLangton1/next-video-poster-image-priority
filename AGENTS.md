# next-video

## Package manager
This project uses bun (1.4 or later, which reads `bun.lock`) to install packages and run scripts. TypeScript, esbuild and the Node test runner still run on Node.
- Install: `bun install` (CI and fresh checkouts: `bun install --frozen-lockfile`).
- Scripts: `bun run <script>`. Tests are `bun run test`, never plain `bun test` (that starts bun's own test runner, not Node's). One-off tools: `bunx <tool>`.
- Add or remove packages with `bun add` / `bun remove`, and commit `bun.lock`. Never use npm, npx or `package-lock.json`.
- Releases still need npm, which comes with Node: `wet-run` in the CD workflow runs `npm version` and `npm publish` and fetches its release helpers with `npx`. That's why CD keeps `setup-node` with the registry URL.
