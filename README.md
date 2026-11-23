# Fancy Text Generator

Turn plain text into **22 fancy Unicode font styles**: bold, italic, cursive, gothic, double-struck, bubble, small caps, fullwidth, upside down and more. You can copy and paste the result into Instagram bios, TikTok, WhatsApp, Discord, X, YouTube and game names.

- Zero dependencies, about 10 KB of plain JavaScript (under 4 KB gzipped)
- Works in Node.js 18+, modern browsers, Deno and Bun
- Includes `toPlain()` to turn fancy text back into normal text
- Includes a small command-line tool
- MIT licensed

**Online version (500+ styles, no install):** https://fancytextgenie.com

```text
bold             𝐅𝐚𝐧𝐜𝐲 𝐓𝐞𝐱𝐭 𝟏𝟐𝟑
boldScript       𝓕𝓪𝓷𝓬𝔂 𝓣𝓮𝔁𝓽 123
fraktur          𝔉𝔞𝔫𝔠𝔶 𝔗𝔢𝔵𝔱 123
smallCaps        ꜰᴀɴᴄʏ ᴛᴇxᴛ 123
circled          Ⓕⓐⓝⓒⓨ Ⓣⓔⓧⓣ ①②③
upsideDown       ƐᄅƖ ʇxǝʇ ʎɔuɐɟ
```

## Install

```bash
npm install fancytextgenie
```

## Usage

### JavaScript

```js
import { convert, convertAll, toPlain, listStyles } from 'fancytextgenie';

convert('Hello world', 'boldScript');
// '𝓗𝓮𝓵𝓵𝓸 𝔀𝓸𝓻𝓵𝓭'

convertAll('Hi');
// [{ id: 'bold', name: 'Bold (serif)', text: '𝐇𝐢' }, ...]

toPlain('𝓗𝓮𝓵𝓵𝓸 𝔀𝓸𝓻𝓵𝓭');
// 'Hello world'

listStyles();
// [{ id: 'bold', name: 'Bold (serif)' }, ...]
```

### Browser (no build step)

```html
<script type="module">
  import { convert } from 'https://cdn.jsdelivr.net/npm/fancytextgenie/+esm';
  document.querySelector('#out').textContent = convert('Hello', 'fraktur');
</script>
```

### Command line

```bash
npx fancytextgenie "Fancy Text"              # every style
npx fancytextgenie "Fancy Text" -s circled   # one style
npx fancytextgenie -p "𝓕𝓪𝓷𝓬𝔂 𝓽𝓮𝔁𝓽"            # back to plain text
npx fancytextgenie --list                    # all style ids
```

## Styles

| id | Name | Example |
|---|---|---|
| `bold` | Bold (serif) | 𝐅𝐚𝐧𝐜𝐲 𝐓𝐞𝐱𝐭 𝟏𝟐𝟑 |
| `italic` | Italic (serif) | 𝐹𝑎𝑛𝑐𝑦 𝑇𝑒𝑥𝑡 123 |
| `boldItalic` | Bold italic (serif) | 𝑭𝒂𝒏𝒄𝒚 𝑻𝒆𝒙𝒕 123 |
| `script` | Script / cursive | ℱ𝒶𝓃𝒸𝓎 𝒯ℯ𝓍𝓉 123 |
| `boldScript` | Bold script / cursive | 𝓕𝓪𝓷𝓬𝔂 𝓣𝓮𝔁𝓽 123 |
| `fraktur` | Gothic (Fraktur) | 𝔉𝔞𝔫𝔠𝔶 𝔗𝔢𝔵𝔱 123 |
| `boldFraktur` | Bold gothic (Fraktur) | 𝕱𝖆𝖓𝖈𝖞 𝕿𝖊𝖝𝖙 123 |
| `doubleStruck` | Double-struck / outline | 𝔽𝕒𝕟𝕔𝕪 𝕋𝕖𝕩𝕥 𝟙𝟚𝟛 |
| `sans` | Sans-serif | 𝖥𝖺𝗇𝖼𝗒 𝖳𝖾𝗑𝗍 𝟣𝟤𝟥 |
| `sansBold` | Sans-serif bold | 𝗙𝗮𝗻𝗰𝘆 𝗧𝗲𝘅𝘁 𝟭𝟮𝟯 |
| `sansItalic` | Sans-serif italic | 𝘍𝘢𝘯𝘤𝘺 𝘛𝘦𝘹𝘵 123 |
| `sansBoldItalic` | Sans-serif bold italic | 𝙁𝙖𝙣𝙘𝙮 𝙏𝙚𝙭𝙩 123 |
| `monospace` | Monospace / typewriter | 𝙵𝚊𝚗𝚌𝚢 𝚃𝚎𝚡𝚝 𝟷𝟸𝟹 |
| `fullwidth` | Fullwidth / vaporwave | Ｆａｎｃｙ　Ｔｅｘｔ　１２３ |
| `smallCaps` | Small caps | ꜰᴀɴᴄʏ ᴛᴇxᴛ 123 |
| `circled` | Bubble (circled) | Ⓕⓐⓝⓒⓨ Ⓣⓔⓧⓣ ①②③ |
| `circledNegative` | Bubble filled | 🅕🅐🅝🅒🅨 🅣🅔🅧🅣 ❶❷❸ |
| `squared` | Squared | 🄵🄰🄽🄲🅈 🅃🄴🅇🅃 123 |
| `squaredNegative` | Squared filled | 🅵🅰🅽🅲🆈 🆃🅴🆇🆃 123 |
| `upsideDown` | Upside down | ƐᄅƖ ʇxǝʇ ʎɔuɐɟ |
| `strikethrough` | Strikethrough | F̶a̶n̶c̶y̶ ̶T̶e̶x̶t̶ ̶1̶2̶3̶ |
| `underline` | Underline | F̲a̲n̲c̲y̲ ̲T̲e̲x̲t̲ ̲1̲2̲3̲ |

Characters a style doesn't cover (punctuation, accented letters, emoji) are kept as they are.

## How it works

These aren't fonts. Social apps don't let you change fonts, so each "font" is a set of different Unicode characters that happen to look like styled letters.

- **Bold, italic, script, gothic, double-struck, sans-serif and monospace** come from the *Mathematical Alphanumeric Symbols* block (U+1D400–U+1D7FF). Mathematicians use these to tell variables apart, for example 𝐱 vs 𝑥.
- **A few letters are missing from that block** because they were added to Unicode earlier, in the *Letterlike Symbols* block. For example, script B is `ℬ` (U+212C) and double-struck R is `ℝ` (U+211D). This library maps those gaps correctly. Naive converters leave empty boxes there.
- **Bubble and squared letters** come from the *Enclosed Alphanumerics* blocks. **Fullwidth** text comes from the *Halfwidth and Fullwidth Forms* block.
- **Strikethrough and underline** add a combining mark (U+0336, U+0332) after each character.
- **Upside-down text** swaps each character for a look-alike rotated character, then reverses the order.

## Before you use fancy text

- **Screen readers:** many screen readers read math letters one by one ("mathematical bold capital H…") or skip them. Keep important text, such as your name or a call to action, in plain text.
- **Older phones:** some styles show as empty boxes (tofu) on older Android versions and in a few apps. Test on a real device before you commit to a style.
- **Character limits:** most styled letters sit outside the Basic Multilingual Plane, so they count as **2** toward many length limits. `measure()` shows both counts:

  ```js
  import { measure } from 'fancytextgenie';
  measure('𝐇𝐢'); // { codePoints: 2, utf16Units: 4 }
  ```

- **Search:** most search engines and in-app search features won't match `𝓗𝓮𝓵𝓵𝓸` to "hello". Use `toPlain()` before you index or compare text.

## API

| Function | Returns | Description |
|---|---|---|
| `convert(text, styleId)` | `string` | Converts text to one style. Throws on an unknown style id. |
| `convertAll(text)` | `{ id, name, text }[]` | Converts text to every style. |
| `toPlain(text)` | `string` | Turns fancy text back into plain text (all styles except `upsideDown`). |
| `measure(text)` | `{ codePoints, utf16Units }` | Counts characters both ways. |
| `listStyles()` | `{ id, name }[]` | Lists all styles. |

TypeScript types are included.

## Contributing

Issues and pull requests are welcome. If you add a style:

1. Add it to `src/styles.js`.
2. Add a test in `test/index.test.js`.
3. Run `npm test`.

Only use assigned Unicode code points that display on current iOS, Android, Windows and macOS.

## License

[MIT](LICENSE) © FancyTextGenie. Website: https://fancytextgenie.com
