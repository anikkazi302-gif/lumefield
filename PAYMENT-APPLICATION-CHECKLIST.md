# LumeField — Payment Application Checklist

**Date:** 2026-11-11
**Site:** https://anikkazi302-gif.github.io/lumefield/ (GitHub Pages, static site, no backend)
**Status:** site-side groundwork DONE (Buy credits section, Terms §8 billing + refunds, Privacy Payments section). Checkout is NOT live — no gateway account exists yet, no application has been submitted.

**Ground rule — read first:** the owner submits everything below **directly on Paddle's and Polar's own websites**, with his own hands, in his own browser. He never sends his ID, bank details, or any document to the assistant in chat, and never to anyone by email. The assistant never sees or handles his documents.

---

## 0. Pricing decision (owner approves first — nothing is final yet)

Proposed credit packs (fit the credit costs 5s = 4, 10s = 7, 20s = 14, 30s = 20; floor $4.99, because fees eat ~15% of a smaller sale):

| Pack | Credits | Price | What it buys | Paddle fee (5% + $0.50) | Owner keeps |
|---|---|---|---|---|---|
| **Starter** | 60 | **$4.99** | 3 × 30s videos (or 15 × 5s, 8 × 10s) | $0.75 | $4.24 |
| **Plus** | 150 | **$9.99** | 7 × 30s videos (10 credits left over) | $1.00 | $8.99 |
| **Ultra** | 300 | **$19.99** | 15 × 30s videos | $1.50 | $18.49 |

Per 30-second video: $1.66 / $1.43 / $1.33. Polar's fee is 5% + $0.50 + 1.5% on non-US cards, so a few cents more per sale — the packs stay the same, the keeper column is a few cents lower on Polar.

The owner must approve these prices (or change them) before any product is created in a gateway dashboard. The site shows them as **proposed** until then.

---

## 1. What the owner prepares (in order)

| # | Item | Details | Cost |
|---|---|---|---|
| 1 | **Approve the prices above** (or set different ones) | One decision: Starter / Plus / Ultra prices. Nothing else can be built until this is chosen. | $0 |
| 2 | **Payoneer account** (free to open) | Sign up at payoneer.com with the same ID and bank account below. This is how Paddle's payouts reach him without the $15 SWIFT wire fee. (Annual fee $29.95 only if under $6,000 received in 12 months.) | $0 |
| 3 | **Government ID** — NID card or passport | Clear photo/scan, front and back. Needed for KYC identity checks on Paddle (Sumsub), Polar (Stripe Connect Express) and Payoneer. | $0 |
| 4 | **Proof of address** — utility bill or bank statement in his name | Sometimes asked by Paddle's verification. Have one ready, dated within the last 3 months. | $0 |
| 5 | **Bank account in his own name, in Bangladesh** | Payout destination (or the account Payoneer withdraws to, in BDT). Account number + bank name + branch. | $0 |
| 6 | **An email he controls** | For the gateway accounts, payout notices, and customer support. His Gmail (anikkazi302@gmail.com) is already used for Firebase — use the same one so everything stays in one place. | $0 |
| 7 | **Live site with Terms, Refund Policy, Privacy Policy, pricing** | DONE in this push: Terms §7–§8 (credits, billing, 7-day refund), Privacy Payments section, Buy credits section with packs. Paddle's domain review checks these pages. | $0 (team work) |
| 8 | **Custom domain lumefield.com (recommended, later)** | ~$10–15/year. Paddle verifies that the seller owns the domain he sells from — a `github.io` address belongs to GitHub, not to him, and may fail that check. If there is no money for a domain yet, apply to Polar first (it may accept the github.io address) and buy the domain before the first real sale. | ~$10–15/year |

**He does NOT need:** a registered company, a US company, a Stripe account, a PayPal account, or any money upfront to apply.

---

## 2. Apply — Paddle AND Polar at the same time (free to apply)

Apply to both in parallel and use whichever approves first. Approval is **not guaranteed** — Paddle in particular rejects sellers without giving a reason. That is why there are two applications, not one.

### 2.1 Paddle (1st choice)

1. Go to **paddle.com** → sign up as a seller (individual, Bangladesh).
2. Fill in the business details: product name **LumeField**, website **https://anikkazi302-gif.github.io/lumefield/** (or the custom domain once bought), product description (free AI video generator; credit packs), contact email.
3. Complete identity verification (Sumsub): upload the NID/passport + proof of address from step 1. Sometimes a short liveness video is asked for.
4. Add a payout method: **Payoneer** (preferred — avoids the $15 SWIFT fee) or bank wire. Minimum payout **$100** (adjustable up). Payouts are monthly: balance above the threshold on the 1st is sent by the 15th.
5. **Re-check the fee on Paddle's own pricing page on the day of signup** (published: 5% + $0.50 per sale; Paddle asks sellers of products under $10 to contact sales for custom pricing — check this at signup). Also note: Paddle does **not** refund its fee when a customer is refunded.
6. Once approved, create the 3 products in the Paddle dashboard (Starter / Plus / Ultra, one-time payments, prices from step 0) and copy the hosted checkout links.

### 2.2 Polar (2nd choice)

1. Go to **polar.sh** → sign up (individual, Bangladesh — Bangladesh is explicitly on Polar's seller/payout-country list).
2. Fill in the product details the same way as Paddle.
3. Connect payouts through **Stripe Connect Express** (payout-only rail — this is NOT a Stripe merchant account, which Bangladesh cannot open). Bank account in his own name. New organisations wait 7 days before the first payout; account review can take up to 14 days.
4. **Re-check the fee on Polar's own pricing page on the day of signup** (published Starter: 5% + $0.50 + 1.5% on non-US cards; plus Stripe payout charge $2/month + 0.25% + $0.25 per payout; dispute fee $15).
5. Once approved, create the 3 products (one-time payments) and copy the hosted checkout links.

### 2.3 Backups (only if both fail)

- **Creem** (3.9% + $0.40) — Bangladesh bank payouts carry extra restrictions from its transfer partner; confirm with Creem before relying on it.
- **Gumroad** (10% + $0.50 + 2.9% + $0.30) — works, but the most expensive; weekly payouts, $100 minimum, no Payoneer.
- **Do NOT start on Lemon Squeezy** — it is being wound down into Stripe Managed Payments, which excludes Bangladesh.
- **Never** open a PayPal or Stripe account with a fake foreign address or VPN — such accounts are frozen and the money held for 180 days.

---

## 3. Test before selling (free, no real money moves)

1. In the approved gateway's dashboard, open the **sandbox / test mode** for each of the 3 checkout links.
2. Run a test purchase for each pack (test card from the gateway's docs — no real money).
3. Confirm the test payment email arrives and the amounts match the approved prices.
4. Only after all 3 test checkouts work, tell the team to make the site's Buy buttons live with the real checkout links.

---

## 4. Going live on the site (team work, after approval)

1. Team replaces the disabled "Buy — coming soon" buttons with the real hosted checkout links (Paddle or Polar — whichever approved first).
2. Team removes the "proposed prices" wording and shows the final approved prices.
3. **Manual unlock first:** when a payment email arrives, the owner adds the bought credits to the buyer's wallet by editing the wallet document in the Firebase console (Firestore Database → Data → `wallets/{user-uid}` → set `credits` to old balance + pack credits). This is the ONLY way to add credits — the Firestore security rules only ever let a balance go down by a video cost, so a user can never add credits to their own account, and the site itself has no admin button for it.
4. **Automate later (after the first real sales):** a webhook from the gateway sets the credits automatically. That needs either Firebase Cloud Functions (Blaze plan — a card on file; usage inside the free allowance is $0) or a free-tier serverless function on Vercel/Netlify. Do this only after sales prove the plan works.
5. **Never** put any gateway secret key in the website's public code — secret keys live server-side only. A key in public GitHub code is stolen within hours.

---

## 5. After the first sales (watch these)

- **Refund rate:** the 7-day money-back guarantee is in the Terms. Paddle keeps its fee on refunded sales — a refunded $9.99 sale still costs $1.00 in fees.
- **Chargebacks:** $20 (Paddle) / $15 (Polar) each, not refunded even if the dispute is won.
- **Payouts:** Paddle pays monthly above $100; Polar after review, 7-day hold on the first payout. Export proceeds must come through banking channels (needed for the government's 6% software-export cash incentive — confirm with the bank whether MoR payouts qualify).
- **Tax:** the Merchant of Record handles the *buyer's* sales tax/VAT. The owner's *income* tax in Bangladesh is his own responsibility — talk to his bank or a local accountant once money starts arriving.

---

## সংক্ষেপে (বাংলায়)

- **দাম ঠিক করা বাকি** — Starter ৬০ ক্রেডিট $৪.৯৯, Plus ১৫০ ক্রেডিট $৯.৯৯, Ultra ৩০০ ক্রেডিট $১৯.৯৯ (প্রস্তাব; তুমি হ্যাঁ বললে চূড়ান্ত)।
- **তোমার যা লাগবে:** NID/পাসপোর্ট, ঠিকানার প্রমাণ, নিজের নামে ব্যাংক অ্যাকাউন্ট, ফ্রি Payoneer অ্যাকাউন্ট, আর তোমার ইমেইল। কোম্পানি লাগবে না, আবেদন করতে টাকা লাগবে না।
- **আবেদন:** Paddle আর Polar — দুটোতেই একসাথে আবেদন করবে, **ওদের নিজের সাইটে গিয়ে**, তোমার হাতে। কাগজ কাউকে চ্যাটে দেবে না।
- **অনুমোদন নিশ্চিত না** — Paddle মাঝে মাঝে কারণ না বলে না করে দেয়; তাই দুটোতে আবেদন।
- **চেকআউট চালু হলে** সাইটের "Buy" বোতামে আসল লিংক বসবে; প্রথমে টাকা এলে তুমি Firebase console থেকে হাতে ক্রেডিট যোগ করবে; অটো সিস্টেম পরে।
- **ডোমেইন** lumefield.com (~$১০–১৫/বছর) পরে কিনলে Paddle-এর অনুমোদন সহজ হবে; এখন টাকা নেই বলে Polar দিয়ে শুরু করা যায়।

---

*Sources: `lumefield-payment-plan.md` in this repo (verified against the providers' own pages, Oct–Nov 2026). Fees and country lists change — always re-check the provider's own page on the day of signup. This document is a checklist, not financial, tax or legal advice.*
