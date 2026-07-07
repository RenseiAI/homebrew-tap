# homebrew-tap — RenseiAI/homebrew-tap (public)

Homebrew tap distributing the CLI binaries as casks. Two live casks in
`Casks/`: `rensei.rb` (closed-source platform CLI) and `donmai.rb` (OSS CLI).
`af.rb` / `af-tui.rb`, if present, are legacy AgentFactory-era names — do not
extend them.

## Iron rules

- Cask files are **GoReleaser-generated** (the file header says DO NOT EDIT).
  Never hand-edit a cask -> instead: fix `.goreleaser.yaml` in the shipping
  repo (`rensei-tui` for `rensei.rb`, `donmai` for `donmai.rb`) and re-release;
  the release workflow pushes the regenerated cask here.
- Binaries are hosted at `github.com/RenseiAI/releases` — cask URLs must point
  there.
- This repo is public: no private references, no internal paths.
- After a daemon-shipping cask upgrade, users must restart the service
  (`brew services restart rensei|donmai`) — an old resident daemon exec's a
  dead versioned Caskroom path. Mention this in release notes when the daemon
  changes.
