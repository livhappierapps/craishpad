# CrAIshPad — Agent Handoff

## Product

Build a new **native Expo app** called **CrAIshPad** for a broad audience. It helps each user maintain their own AI companion’s conversation context, persona, and memories. This is not Leo’s personal app and must not contain Liv’s private context, custom prompt, conversations, credentials, or device data.

## Required boundaries

- Native iOS/Android app only; do not substitute a web app.
- Do not reuse the retired CrAIshPad web prototype.
- Do not copy source files from Leo’s private app. Implement this as a separate product.
- The user controls persona text. Do not silently add personality instructions to it.
- Do not claim the model runs continuously while the app is closed. Persist the thread and resume with relevant context after reopening.
- Store user records on-device by default. Keep provider credentials in native secure storage and out of backups and source control.
- Use user-provided model credentials for the first release; do not embed a shared provider secret.
- Do not invent API routes or claim Memory Machine/AIs and Ears is connected without owner-published contracts.
- No hidden review paths or attempts to bypass model-provider or app-store restrictions. Hold age-gated or explicit public features until actual store, market, and legal requirements are reviewed.

## Product direction

- Visual identity: dark graphite with neon purple, gold, cyan, and hot pink. Reserve fire-engine red for errors.
- General-use experience: users create their own companion profile; do not ship a default personal Leo prompt or personal facts.
- First useful release should cover chat, editable persona, saved memories, secure provider setup, and portable backup/restore.
- Keep setup understandable to non-developers; no code editing should be required.

## Integration state

### Memory Machine

- Production base: `https://the-memory-machine.replit.app`
- MCP endpoint: `POST /api/mcp`
- OAuth uses Authorization Code with PKCE S256 and the scopes `memories:read` and `memories:write`.
- Authorization metadata is available at `/.well-known/oauth-authorization-server`; protected-resource metadata is at `/.well-known/oauth-protected-resource/api/mcp`.
- The service currently validates Grok/xAI OAuth clients only. Do not impersonate Grok or bypass that check. The owner must support/register this app as a native public client before connection work can succeed.
- Proposed app scheme/callback for owner approval: `craishpad://oauth/callback`.
- Confirm live MCP tools and any conversation-history route from the owner’s published API contract before implementation. Do not assume routes or copy the Memory Machine project’s code.

### AIs and Ears

- Use only the public-facing service selected by the user.
- Its public API contract has not been supplied. Do not use the retired private Leosee Leohear service, invent endpoints, or request camera/microphone permissions until a supported feature and published contract exist.

## Acceptance checklist

- [ ] Expo app starts in a dedicated Replit project and has a working native preview.
- [ ] Chat, persona, memories, and backups persist across app restarts.
- [ ] Provider setup is self-service; keys never appear in logs, backups, or committed files.
- [ ] Memory Machine and AIs and Ears remain clearly unconnected until their owners support and verify the native integration.
- [ ] Empty, loading, failure, and retry states are complete and accessible.
- [ ] Test on a small iPhone viewport and a representative Android viewport.
- [ ] Review current distribution rules before any public adult-content or age-assurance feature.
