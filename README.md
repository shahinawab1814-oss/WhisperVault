# WhisperVault — Vercel + Firebase

## Behavior
Every submitted confession/story is published immediately to the public feed as `Anonymous Persona`. The public never sees the submitter name or email. The creator/admin can sign in at `/admin.html` and see the private name, email, original story, category, mood and date.

## Firestore collections
`publicPosts/{postId}` contains only public fields: text, category, mood, theme, status, createdAt.

`privateSubmissions/{postId}` contains realName, email, original text and other submission details. Non-admin users cannot read this collection.

## Firebase
Project: `whispervault-3588e`
Admin: `shahinawab1814@gmail.com`
Authentication: Email/Password
Firestore: Production mode

Copy `firestore.rules` into Firebase Console → Firestore Database → Rules and Publish.

After Vercel deployment, add the Vercel hostname (without https://) to Firebase Console → Authentication → Settings → Authorized domains.

## GitHub
Upload the contents of this folder to the repository root. Do NOT upload Firebase service-account JSON/private keys, passwords or tokens.

## Vercel
Import the GitHub repository. Framework: Other. Build command: blank. Output directory: `.`. Install command: blank. Deploy. No Vercel environment variables are required by this direct Firebase web-SDK version.

## Test
1. Submit a test confession with a test name/email.
2. Confirm the public feed shows the story as Anonymous Persona.
3. Confirm the public page does not show name/email.
4. Open `/admin.html` and sign in with `shahinawab1814@gmail.com`.
5. Confirm the private table shows name/email/story.
6. Test CSV, comments and reactions.

## Safety
The product requirement is immediate public publication of submitted content. Before a large public launch, add Firebase App Check, abuse/rate limiting, reporting and monitoring. Prohibit illegal content, threats, doxxing, exploitation, non-consensual intimate imagery and sexual content involving minors.
