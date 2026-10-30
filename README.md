# Slack · plugin for Escouade

Tickets to test and agents waiting, in each project’s Slack channel. A TypeScript program that calls `chat.postMessage`; the bot’s token is kept in the keychain.

At install, Escouade asks for a bot token (`xoxb-…`, scope `chat:write`). Each project posts to the channel `channels.json` names for it, or to `escouade-<project>`. Escouade runs `dist/plugin.mjs` with Node. A ticket’s title is escaped (`&`, `<`, `>`) as Slack asks: a `<!channel>` from a public issue shows without notifying anyone. Installed from the store, `channels.json` is the one of this repository (its fingerprint is checked): to choose your channels, fork the plugin; otherwise each project posts to `escouade-<project>`.

> Les tickets à tester et les agents qui attendent, dans le salon Slack de chaque projet. Un programme TypeScript qui appelle `chat.postMessage` ; le jeton du bot est gardé au trousseau.

One of the example plugins of [Escouade](https://escouade.dev) (id `dev.exemple.slack`), published on its store: https://store.escouade.dev. The documentation shows it whole: https://escouade.dev/en/docs/plugins/examples

## Develop

```sh
npm install
npm test            # against the fake Escouade of @escouade-dev/plugin
npm run build       # dist/plugin.mjs, the file Escouade runs (committed)
npm run validate    # escouade-plugin validate .
npm run bench       # Escouade's conformance bench
```

## Try it in Escouade

Plugins view › “In development”, then this folder; or install it from the store.

## License

MIT (`LICENSE`).
