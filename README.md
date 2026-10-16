# Bugga AI — working realtime voice MVP

A mobile browser voice agent using OpenAI Realtime API + WebRTC, with real tool calling to browser-local tasks and demo orders, and printable demo kitchen tickets.

## Run locally
1. Install Node.js 20+.
2. `npm install`
3. Copy `.env.example` to `.env` and set your OpenAI API key. Never put the key in frontend code.
4. `npm start`
5. Visit `http://localhost:3000` on the same computer.

## Use from a different phone
Deploy the Node.js project to a host supporting Node services (for example Render or Railway). Set `OPENAI_API_KEY` as a **server-side environment variable** in the hosting dashboard. Set build command `npm install` and start command `npm start`. Open the resulting HTTPS URL on your phone, grant microphone permission, and tap **Start talking**. A plain static-file host alone will not work because the server must mint temporary session credentials.

## What is real vs demo
- Real: low-latency two-way AI speech over WebRTC, microphone input, model tool calling, task/order creation in local browser storage, print dialog.
- Demo: food orders are not submitted to a real restaurant POS, and print is not unattended kitchen printing. Tasks are not synced between phones.
- No paid phone-number dialing: this is a browser voice call, not a PSTN call.

## Production requirements
Authentication, server-side persistent database, rate limits, audit logs, per-restaurant menu/availability, order confirmation and idempotency, POS API integration, print bridge or POS kitchen routing, monitoring, privacy and retention controls, and payment security. Verify your account's realtime model access and API pricing before deployment.
