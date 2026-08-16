# Phishing Awareness Demo

An educational, self-revealing fake scam page for security-awareness training.

## How it works

1. Visitor sees a flashy "70% OFF" flash sale with countdown timers (fake brand: **ShopMega Deals** — no real company impersonated).
2. To "claim the coupon" they enter a phone number, then an OTP.
3. Instead of harvesting anything, the page immediately switches to a **reveal screen**: "You just fell for a phishing pattern" — with an explanation of every red flag they just ignored and 5 golden rules.

## Privacy & safety guarantees

- **No backend, no data collection.** Inputs are format-validated in the browser and then cleared — nothing is stored, sent, logged, or notified anywhere.
- **No real brand impersonation.** Generic fake brand only.
- **Persistent disclosure banner** at the top of the page at all times: "SECURITY AWARENESS DEMO — fake page for training."

## Run locally

Just open `index.html` in a browser, or:

```bash
npx serve .
```

## Deploy to Vercel

```bash
npm i -g vercel
vercel          # from this folder
```

Or push to GitHub and import the repo at vercel.com — it's a static site, zero config needed.

## Completion notifications (optional, anonymous)

You can get a push notification on your phone when someone finishes the demo — **without collecting anything they typed**:

1. Install the free **ntfy** app ([ntfy.sh](https://ntfy.sh)) on your phone.
2. Subscribe to a unique, hard-to-guess topic, e.g. `shopmega-demo-x7k2p9q`.
3. In `index.html`, set `const NOTIFY_TOPIC = 'shopmega-demo-x7k2p9q';`

The page then sends a single "Someone completed the phishing awareness demo ✅" message when a visitor reaches the reveal screen. Phone numbers and OTPs are validated and discarded in the browser — their values are never read into any request.

Note: ntfy topics are public to anyone who knows the name, so pick an unguessable one. Leave `NOTIFY_TOPIC` empty to disable.

## Use responsibly

Use this only for awareness training where participants understand they're viewing a demo (the banner makes that explicit). Do not rebrand it to imitate real companies or add data collection.
