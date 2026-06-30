# Translating the bot

Want the bot in your language? It's just one file.

## How

1. Copy `en-US.json` and rename it to your language code, like `de-DE.json` or `es-ES.json`.
2. At the very top there's a `_meta` line:

   ```
   "_meta": { "name": "English (US)", "order": 0 },
   ```

   Change `name` to your language's name written in that language (e.g. `Deutsch`, `Español`, `日本語`) - that's what shows in the `/language` picker. Leave `order` alone (or drop it; it only nudges where your language sits in the list). `_meta` is the ONE non-translatable line - don't translate it, just set the name.
3. Open it. Every other line looks like this:

   ```
   "tracking.removed_title": "✅ User Removed",
   ```

   The left side (`tracking.removed_title`) is an ID - **never touch it**.
   The right side (`✅ User Removed`) is the text - **translate that**.

4. Translate every right-side value. Leave the left side and the structure alone.

## Rules (just a few)

- **Keep `{things}` in curly braces exactly as they are.** They get filled in with real values.
  `"Added {user} to {group}"` → translate the words around them, keep `{user}` and `{group}`.
  Don't rename them or invent new ones. (One exception: a lone `{s}` is an English
  "add an s for plural" helper - if your language doesn't work that way, just leave it out.)

- **Keep the `\n` bits.** Those are line breaks.

- **Keep \`code\` in backticks as-is.** Command names like `/adduser`, `/settings`, `SRZ-XXXX` - don't translate those, people type them literally.

- **Emoji stay.** ✅ 📺 ⭐ etc - leave them, just translate the words next to them.

- **Don't translate `en-US.json` itself.** That's the English original / fallback. Make a new file for your language.

- **Keep it short-ish.** Some spots are buttons or dropdowns with tight space. If your translation is way longer than the English, it might get cut off. An automated check warns us if something's too long, so don't stress about it.

## Missing a key? That's fine

If your file is missing some lines, those just show in English instead of breaking. So you can translate part of it, ship it, and finish later.

Once a file is around **40-50% done** it can already be considered for the live build - you don't have to finish it all at once. Feel free to take it in steps and send updates slowly until it's complete.

Send the file over whenever (partway is fine) and it'll get checked before going live.
