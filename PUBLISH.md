# Publishing to GitHub Pages

Repository: `NandorHU/XDriverSwapper`.
Public page: `https://nandorhu.github.io/XDriverSwapper/`.

1. Create a public repository named `XDriverSwapper` under `NandorHU`.
2. Commit this package's contents to its `main` branch. Upload the files and
   folders inside `XDriverSwapper-GitHub`, rather than that containing folder.
3. In repository **Settings → Pages**, choose **Deploy from a branch**,
   branch **main**, folder **/docs**, and save.
4. Wait for the Pages deployment to finish. Open the returned Pages address and
   verify the two ZIP downloads and both languages.

Official guide:
https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

The website is plain HTML/CSS/JavaScript with relative asset and download paths.
It needs no build, npm dependencies, external fonts, account system or server.
`.nojekyll` ensures it is served as a static page.

## Updating a release

Replace the portable and corresponding source archives in `docs/downloads`.
Update both download links, version text, actual size and SHA-256 in `docs/index.html`,
as well as the README. Keep the download file contents identical to the verified release.

## What was checked locally

- Every local link/image/download resolves to an included file.
- Both archives pass CRC validation and match the supplied release bytes.
- Every translation key has English and Hungarian content.
- JavaScript syntax is valid; language changes update text and persist the selection.
- Relative paths support the GitHub Pages project subdirectory.

GitHub Pages uses the main branch and /docs folder. Recheck both languages and download hashes after each release update.
