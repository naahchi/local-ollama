LOCAL OLLAMA STUDIO — GitHub Pages version

FILES
- index.html: upload this file to the root of your GitHub Pages repository.
- README_HI_EN.txt: setup and troubleshooting guide.

PUBLISH ON GITHUB PAGES
1. Upload index.html to the root of your repository.
2. Open repository Settings -> Pages.
3. Choose Deploy from a branch, select main and /(root), then Save.
4. Open https://naahchi.github.io/local-ollama/ (or your own Pages URL).

WHAT'S INCLUDED
- English default, Hindi/English selector; selected language is saved in localStorage.
- Installed model list, refresh, download/pull by model name, and delete with confirmation.
- Streaming chat and chat history in IndexedDB; resume, rename, and delete saved chats.
- Permission status check where the browser supports it, plus troubleshooting guidance.
- Frontend is static. Each visitor uses their own local Ollama and their own browser's local chat history.

IMPORTANT: FIX OLLAMA CORS (WINDOWS)
The screenshot's CORS error means the browser reached the local Ollama URL but the response did not allow the GitHub Pages origin. This is different from having no models installed.

1. Quit Ollama completely from the Windows system tray (right-click Ollama -> Quit/Exit). Do not just close the browser.
2. Open Command Prompt and run:
   setx OLLAMA_ORIGINS "https://naahchi.github.io"
3. Start Ollama again from the Start menu. If Ollama is already running in the background, fully quit it first so it reads the new environment variable.
4. Reload the GitHub Pages site and click Refresh models.

If you host the page at a different origin, use that exact origin instead. If you already rely on other custom Ollama origins, preserve them as a comma-separated list rather than replacing them accidentally. Do not use a wildcard origin unless you fully understand the security implications.

BROWSER PERMISSION
- Click “Check permission” to show the permission status if the browser exposes it.
- Click “Fix permission” for instructions. The website cannot silently change a permission that was blocked by the user.
- In Chrome, open Site settings for https://naahchi.github.io and allow Local network access if that setting is available in your version.
- Then click “Refresh models” again.

SECURITY
- Do not expose port 11434 to the public internet.
- Only allow origins you trust.
- Chat history stays in the same browser profile on the same device; it does not sync to other devices and can be erased if browser data is cleared.
- A browser may not expose a readable local-network permission status. In that case, use the connection test and the displayed troubleshooting guidance.

If the browser still reports CORS after setting OLLAMA_ORIGINS, confirm that Ollama was fully quit and restarted and that the allowed origin exactly matches the site's origin (scheme + host, without a page path).
