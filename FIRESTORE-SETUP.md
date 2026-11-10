# Firestore security rules — setup guide (one-time, ~2 minutes)

The credit system is built into the site, but the server-side enforcement
only starts working after these rules are published in the Firebase console.
Until then, signed-in users see a "wallet not connected yet" note and fall
back to the 3 free videos — nothing breaks.

## What to paste

File: `firestore.rules` (in this repo). It lets a signed-in user read and
write ONLY their own wallet document (`wallets/{their user id}`):

- create: only with exactly 60 credits
- update: credits may only go DOWN by 4, 7, 14 or 20 (one video's cost)
- delete: never; everything else in the database: denied

## Steps (the site owner does this in the Firebase console)

1. Open https://console.firebase.google.com and pick the **lumeField** project.
2. Left menu: **Build → Firestore Database**.
3. Click the **Rules** tab (next to Data).
4. Delete everything in the rules editor.
5. Paste the entire contents of `firestore.rules` from this repo.
6. Click **Publish**, then wait for the "Rules published" confirmation.

## How to check it worked

1. Open https://anikkazi302-gif.github.io/lumefield/ and sign in.
2. The bar above the tool should say: "💎 Your credits: 60".
3. Build a 30-second video plan — the bar should drop to 40.
4. If the bar still says "wallet is not connected yet", the rules were not
   published — repeat the steps above.

## Honest limits

- The 3 free videos without login are counted in the visitor's browser
  (localStorage). Clearing browser data resets that count — there is no
  account to tie them to, so that part cannot be enforced server-side.
- These rules stop anyone from raising their own credit balance or touching
  another user's wallet. They cannot stop someone from making a second
  free account (email or Google) — no free system can.
