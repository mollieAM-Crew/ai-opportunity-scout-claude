# AI Opportunity Scout for Claude

Find your highest-value AI next move using relevant context available in Claude. Scout looks at your work, current goals, recurring tasks, bottlenecks, and existing AI habits to identify a useful workflow you may be missing. It gives you one complete recommendation with a small first experiment, plus two previews.

## How it works

Ask **“Where should I be using AI that I am not already?”** Scout’s connector returns a diagnostic framework, and Claude applies it to context actually available in your conversation and enabled Claude features. If there is too little evidence to ground the first recommendation, Scout asks one targeted question. It never implies access to your ChatGPT history.

You can optionally unlock all three recommendations by explicitly agreeing to receive **Watch Me AI**, Mollie Mueller’s practical AI newsletter, and providing your email address. Unsubscribe anytime. The first recommendation remains available if you decline. The full map appears in chat after the signup tool succeeds; finish subscribing by clicking the confirmation link in Kit’s email when required.

## Install and connect

Until the directory listing is published, download or zip this repository’s contents. In Claude, go to **Customize → Plugins → Add → Upload plugin** and select the ZIP. Open the installed plugin’s **Connectors** tab and connect **AI Opportunity Scout**. The Scout connector uses no sign-in or API key from you.

The plugin uses this hosted MCP server: `https://ai-opportunity-scout-claude.vercel.app/mcp`. In Claude Code, load this folder with `claude --plugin-dir ./ai-opportunity-scout-claude`.

## Tools and data handling

- `start_ai_opportunity_scan` checks the service and accepts only an optional brief focus, such as work or career. The diagnostic instructions ship in the plugin files; the server does not supply behavioral instructions. Recommendations are generated inside Claude.
- `subscribe_and_unlock_map` sends your email, optional first name, and explicit consent to the Scout backend, which submits newsletter signup data to Kit with a fixed Claude signup source. It is called only after you agree to receive Watch Me AI.

The plugin does not send raw chat history, memory summaries, files, or opportunity analyses to the Scout backend. It runs no local scripts or hooks, and requires no access to your local environment or credentials. Kit holds newsletter subscriber data; the backend does not keep a separate database of opportunity analyses. Hosting providers process technical delivery data.

Read the [privacy policy](PRIVACY.md) and [service terms](TERMS.md). For support, privacy questions, or deletion requests, email [mollie@molliemueller.com](mailto:mollie@molliemueller.com).

## License

The distributable files in this repository use the [MIT License](LICENSE). This license covers the plugin files; access to the hosted Scout service and newsletter is governed by the service terms, and third-party services have their own terms.
