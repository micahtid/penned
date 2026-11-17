<p align="center">
  <img src="app/icon.svg" alt="Penned icon" width="160">
</p>

# Penned

Penned turns your handwriting into a font so you can write letters that look handwritten.

Draw each character once, write a note, and share it with a link. Anyone who opens the link sees
an envelope, then your letter.

## What It Does

- Draw your own handwriting glyphs, one per character.
- Write notes that render in your handwriting.
- Decorate a note with images, stickers, or drawings.
- Pick a paper style and color.
- Publish a note to get a public link.

## Using It

1. Sign in with Google on the home page.
2. Click Edit Character Set and draw each character once.
3. Create a note and write your message. Notes save automatically.
4. Add images, stickers, or drawings on top.
5. Click Publish, pick a paper style and color, and copy the link.

You can keep up to 10 notes at a time. Delete one to make room for another.

## Sharing

A published letter is a snapshot. It keeps a copy of the glyphs it uses, so the link keeps
rendering the same handwriting even after you redraw your characters.

Public letter links work without an account. Everything else requires signing in.

## How The Code Is Organized

Penned is a Next.js app with a Convex backend and Google sign-in through Convex Auth. Pages live
in `app/`, UI in `components/`, and the schema and server functions in `convex/`.

Convex stores four tables: `glyphs` (your characters), `notes` (drafts), `letters` (published
snapshots), and `letterGlyphs` (the glyphs each letter uses).

## Developing

```bash
npm install
npm run dev
```

`npm run dev` starts Next.js and Convex together. The first run of Convex creates a deployment
and fills in `NEXT_PUBLIC_CONVEX_URL` and `CONVEX_DEPLOYMENT` in `.env.local`.

Google sign-in needs three values set on the Convex side:

```bash
npx convex env set SITE_URL http://localhost:3000
npx convex env set AUTH_GOOGLE_ID <your-client-id>
npx convex env set AUTH_GOOGLE_SECRET <your-client-secret>
```

Run `npm run lint` to check the code and `npm run build` for a production build.
