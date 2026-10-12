LOCAL OLLAMA STUDIO — GitHub Pages version

Files: index.html (the static website) and this guide.

PUBLISH
1. Create a GitHub repository and upload index.html to the repository root.
2. Go to Settings -> Pages.
3. Choose Deploy from a branch, select main and /(root), then Save.
4. Open the published URL.

WHAT'S INCLUDED
- English by default; Hindi/English selector. Choice is saved in localStorage.
- Installed model list, refresh, pull/download by model name, and delete with confirmation.
- Chat streaming and chat history in IndexedDB, including resume, rename, delete.
- Frontend is static. Models remain in each user's local Ollama.

IMPORTANT LOCAL CONNECTION NOTES
This page calls http://127.0.0.1:11434 on the computer running the browser. GitHub Pages itself does not run Ollama.
A GitHub Pages HTTPS page may be blocked from reaching local Ollama by CORS or browser security rules. If you see a CORS/network error, configure Ollama's allowed origins using the official Ollama documentation for your operating system and allow only the exact Pages origin you trust. Fully restart Ollama after changing its environment.
If direct HTTPS-to-localhost requests remain blocked, a small local companion/bridge is required; GitHub Pages alone cannot bypass browser security.
Do not expose port 11434 to the public internet. Do not casually use wildcard origins.
Chat history stays in this browser profile on this device and does not sync to other devices. Browser data can be cleared.
