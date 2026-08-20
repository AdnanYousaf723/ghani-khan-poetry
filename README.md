# Ghani Khan Poetry

A static, browser-based Pashto poetry archive with source scans, spoken Roman Pashto, English translation, and built-in music playback.

This version follows the Stitch prototype direction:

- mobile-first archive layout
- book-style paper texture and framed poem cards
- top app bar and bottom mobile navigation
- one search panel with poem and song suggestions
- poem cards with source scan on one side and poem music on the other
- Pashto, spoken Roman Pashto, and English columns
- a separate Music Room for all available recordings
- including poems with no song yet

## Run locally

No build tools are required. Open `index.html` in a browser.

For the most reliable local testing, run a small local server:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Deploy on a Linux Server

Upload the full project folder to your web server and serve `index.html` as a static site.

Example folder path:

```text
/var/www/ghani-khan-poetry/
```

The server must keep these folders together:

```text
index.html
assets/audio/
assets/source/
```

For Nginx, the site root should point to the project folder:

```nginx
server {
    listen 80;
    server_name your-domain.com;
    root /var/www/ghani-khan-poetry;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

Replace `your-domain.com` with your real domain.

## Music

The recordings live in:

```text
assets/audio/
```

The website currently includes 21 local MP3 files from the provided archive. Some poems have more than one version, and poems without music stay visible with a no-song message.

The player supports:

- play / pause
- seek slider
- elapsed and duration time
- volume control
- poem title and performer/source reference

Only publish recordings after you have permission to use and redistribute them.

## Source Verification

The supplied PDF scans are kept as the visual source of truth. Each poem has a source-scan button and an inline scan preview so readers can compare the text with the original page.

The Pashto text has been cleaned conservatively. Roman Pashto is written in a natural spoken reading style, not as a strict academic romanization.

## GitHub Pages

This project is static HTML/CSS/JavaScript and can be deployed directly with GitHub Pages.

## Rights Note

This archive contains poetry, translation, scans, and recordings that may require permission before public redistribution. The publisher of the site is responsible for getting those permissions before release.

## Credits

- Poetry: Ghani Khan
- English translation: Taimur Khan, as credited in the supplied source PDF
- Digital edition, Roman Pashto, interface, and archive work: Adnan Yousaf
- Email: `adnanyousafair13164@gmail.com`
- Public contact: Instagram `@adnan_yousaf723`
