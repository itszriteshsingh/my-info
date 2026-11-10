# Thakur Music — Vercel

Premium responsive music website with search, song cards, favourites, queue, mini-player and full-screen player.

## API configuration

This project uses the Sparrow API settings from the supplied `Youtube.py` file:

- `MUSICSP_API_URL` defaults to `https://apisparrow.site`
- `MUSICSP_API_KEY` is required and is used only on the server in `/api/audio`
- Search uses the `yt-search` package; no YouTube Data API key is needed for this search implementation.

The Sparrow key is never placed in browser JavaScript. Add it in Vercel:
1. Import this project from GitHub.
2. Open Project → Settings → Environment Variables.
3. Add `MUSICSP_API_URL` = `https://apisparrow.site`
4. Add `MUSICSP_API_KEY` = your Sparrow API key.
5. Redeploy.

## Important
The audio route proxies the provider's `/download` endpoint and assumes it returns playable audio bytes, matching the uploaded Python code's expected behavior. Actual availability, limits, and terms depend on the API provider. Use only content you are authorized to access and play. Some tracks may fail if the provider restricts them.

## Deploy
Run `npm install` then `npm run build`, or import the GitHub repository into Vercel. Node.js 18.17+ recommended.


## Build fix
`cheerio` is explicitly listed as a dependency because the YouTube search package requires it during Vercel server build/runtime.
