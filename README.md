# devsamarth_v3

This here is my personal website. Feel free to use this as inspiration but do not copy.

## Development

Use [Bun](https://bun.sh) 1.3.14 or newer from this directory:

```sh
bun install
bun run dev
```

The website is in `devsamarth_v3/`. This root package is a Bun workspace, and its
commands forward to the website:

```sh
bun run lint
bun run build
bun run preview
bun run deploy
```

Deployment still uses `gh-pages` to publish `devsamarth_v3/dist` to the existing
`gh-pages` branch at **https://devsamarth.com**. Run the build before deployment.

See [the website guide](devsamarth_v3/README.md) for Markdown publishing, content
editing, and the small app structure. The design brief is in
[Website_Revamp.md](Website_Revamp.md).
