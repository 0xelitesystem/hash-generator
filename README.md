# Hash Generator

Compute MD5, SHA-1, SHA-256, and SHA-512 hashes from text or a file, entirely in your browser.

**Live demo:** https://0xelitesystem.github.io/hash-generator/

## Use

1. Open the page.
2. Pick **Text** and type or paste, or pick **File** and choose (or drop) a file.
3. All four digests appear at once and update as you type. Toggle **Uppercase hex** if you need it, and click **Copy** on any row.

The text field is encoded as UTF-8 before hashing, so the byte count shown matches what a command-line tool like `md5sum` or `sha256sum` would see. File hashes are computed over the exact bytes on disk.

SHA-1, SHA-256, and SHA-512 use the browser's built-in SubtleCrypto. MD5 is not part of SubtleCrypto, so it is implemented directly from RFC 1321 in the page. MD5 and SHA-1 are kept for checksum and legacy verification work; neither is suitable for security purposes.

## Why this exists

Most "online hash" sites send your text or file to a server, wrap the result in ads and trackers, and give you no way to know what happened to the data. This is one HTML file with no backend, no analytics, and no third-party requests. You can read every line, save it, and run it offline forever. MIT licensed, so you can fork it or vendor it into your own project without asking.

## Privacy

Everything runs in your browser. Your text and files are hashed locally and never leave your machine. There is no server, no upload, no logging, and no network request of any kind. Load the page once and you can disconnect entirely.

## Run locally

Clone and open the file directly:

```
git clone https://github.com/0xelitesystem/hash-generator.git
cd hash-generator
```

Open `index.html` in any modern browser. To serve it over `http://localhost` (which guarantees SubtleCrypto is available), run:

```
python -m http.server
```

Then visit `http://localhost:8000/`.

## Build

There is no build step and no dependencies. The entire tool is a single `index.html` with inline CSS and JavaScript.

## License

MIT. See [LICENSE](LICENSE).

## Related

- https://github.com/0xelitesystem/jwt-inspector
- https://github.com/0xelitesystem/eeat-signals-reference
