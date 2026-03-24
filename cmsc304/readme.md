
# Course Readings Iframe Workflow

Prof's workflow for embedding course readings in an iframe when the original site blocks embedding (via `robots.txt`, `X-Frame-Options`, etc.).

## Prerequisites

- [SingleFile](https://github.com/nicls/single-file) browser extension installed
- This GitHub repo with GitHub Pages enabled (Settings → Pages → Source: `main` branch)

## Steps

1. **Save the page locally.**
   Open the reading in your browser and use the SingleFile extension to save it as a single `.html` file.

2. **Upload the file to this repo.**

3. **Build the GitHub Pages URL.**
   Take the file path in the repo and put it after the Pages base URL:

   ```
   https://rmwillia-umbc.github.io/course-readings/<course>/<filename>.html
   ```

   For example, a file at `cmsc304/some-article.html` becomes:

   ```
   https://rmwillia-umbc.github.io/course-readings/cmsc304/some-article.html
   ```

   If the filename has special characters, you'll need to URL-encode them (spaces → `%20`, etc.). The easiest way is to navigate to the file on the Pages site and copy the URL from your browser.

4. **Embed with an iframe.**
   Use the Pages URL as the iframe `src`:

   ```html
   <iframe src="https://rmwillia-umbc.github.io/course-readings/cmsc304/some-article.html" width="100%" height="800" frameborder="0"></iframe>
   ```

## Tips

- **Pages can take a minute to deploy.** If the URL 404s right after uploading, wait a minute and try again.

- # Talk Slides & Assets

Slides and supporting assets for my data visualization talk.


## Embedding in Slides.com

Assets are embedded via iframe. If you update a file and the iframe still shows the old version, bump the query string to bust the cache:

```
url/filename.html?v=2
```

Increment `?v=3`, `?v=4`, etc. with each update.

## Notes

- Assets here are things Slides.com can't run natively (interactive HTML/JS)
