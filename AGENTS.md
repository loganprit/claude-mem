# claude-mem contributor notes

- Edit TypeScript source under `src/`. `npm run build` regenerates bundled
  distribution files under `plugin/scripts/` and the viewer under `plugin/ui/`;
  do not hand-edit those generated files.
- Run focused tests with `bun test <path>`. Run `npm run build` when a source
  change affects distributed output.
- `npm run build-and-sync` copies the repository into the installed Claude Code
  marketplace and restarts the local worker. Use it only for requested local
  integration testing.
- Keep `<private>...</private>` stripping before content reaches storage or
  downstream processing. Shared stripping logic lives in
  `src/utils/tag-stripping.ts`.
- User documentation lives in `docs/public/`; update `docs/public/docs.json`
  when adding or moving a page.
- `CHANGELOG.md` is generated during release work; do not edit it by hand.
