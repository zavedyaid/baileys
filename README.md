# 🌱 @zavedyaid/baileys — v1.0.1

<p align="center">
  <img src="https://files.catbox.moe/c5s9g0.jpg" alt="Logo" width="300"/>
</p>

<p align="center">
  <strong>ZavedyaID's restructured v1 build of the itsliaaa-enhanced Baileys v7 fork</strong><br>
  Newsletter media upload fixes • Interactive messages • Albums • Additional message types
  <br><br>
  <a href="https://www.npmjs.com/package/@zavedyaid/baileys">
    <img src="https://img.shields.io/npm/v/@zavedyaid/baileys?style=for-the-badge&logo=npm&color=CB3837"/>
  </a>
  <a href="https://www.npmjs.com/package/@zavedyaid/baileys">
    <img src="https://img.shields.io/npm/dm/@zavedyaid/baileys?style=for-the-badge&logo=npm&color=CB3837"/>
  </a>
  <a href="https://github.com/zavedyaid/baileys">
    <img src="https://img.shields.io/github/stars/zavedyaid/baileys?style=for-the-badge&logo=github&color=181717"/>
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge&color=blue"/>
  </a>
  <a href="https://nodejs.org">
    <img src="https://img.shields.io/badge/node-%3E%3D20-339933?style=for-the-badge&logo=node.js&logoColor=white"/>
  </a>
  <a href="#">
    <img src="https://img.shields.io/badge/ESM%20%26%20CJS-ready-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black"/>
  </a>
</p>

---

## 📖 About This Fork

**@zavedyaid/baileys v1.0.1** is a restructured, ZavedyaID-branded build on top of the `itsliaaa/baileys` enhanced fork (interactive messages, albums, additional message types, newsletter media fixes), which itself builds on the original **[WhiskeySockets/Baileys](https://github.com/WhiskeySockets/Baileys)**.

### 🧬 Credit Chain

| Layer | Contributor | Contribution |
|-------|-------------|--------------|
| **1** | [WhiskeySockets/Baileys](https://github.com/WhiskeySockets/Baileys) | Original library |
| **2** | [Lia Wynn (itsliaaa)](https://github.com/itsliaaa) | Interactive messages, albums, newsletter media fixes, additional message types |
| **3** | **ZavedyaID** | Folder restructuring, packaging, and v1.0.0 rebrand |

All three copyright holders are listed in [`LICENSE`](LICENSE), unchanged from the upstream terms.

> ☕ Support the original enhancements author: [Saweria (itsliaaa)](https://saweria.co/itsliaaa)

---

## ✨ Highlights

This fork is designed for production use with a focus on clarity and safety:

- 🚫 **No obfuscation** — Easy to read and audit.
- 🚫 **No auto-follow** — No automatic newsletter (channel) following behavior.

---

### ⚠️ Important Note from the Original Enhancements Author

> *"I want to clarify two separate attribution issues regarding packages derived from this fork:*
>
> 1. *Direct redistribution of my modifications without attribution — several packages operated by the same individual under multiple npm accounts (`@nuisockets`, `@nuiisatoru`, `@nuiisweetberry`, `@nuiisweety`) redistribute files and modifications originating from this fork while removing contributor credits and modification notes.*
>
> 2. *Rebranded republishes of this fork — packages such as `@lumina-md`, `@sairidev/baileys-new`, `@lordmega/baileys`, `phantom-baileys`, and `nexora-baileys` repackage or republish this fork under different names while failing to preserve proper attribution, credits, or modification notes.*
>
> *To be clear, I am NOT the original maintainer of Baileys. Full credit and respect belong to WhiskeySockets/Baileys.*
>
> ***Forking is completely acceptable. Removing attribution, contributor credits, or modification history is not.** "*

— This ZavedyaID build keeps that same principle: it's a fork built openly on itsliaaa's and WhiskeySockets' work, credited as such, not a clean-room rewrite.

---

> [!NOTE]
> 📄 This project is maintained with limited scope and is not intended to replace upstream Baileys.

---

## 📋 Table of Contents

<details>
<summary><strong>Click to expand</strong></summary>

- [📖 About This Fork](#-about-this-fork)
- [✨ Highlights](#-highlights)
- [🛠️ Internal Adjustments](#%EF%B8%8F-internal-adjustments)
- [📨 Messages Handling & Compatibility](#-messages-handling--compatibility)
- [🧩 Additional Message Options](#-additional-message-options)
- [📥 Installation](#-installation)
- [🌐 Connect to WhatsApp](#-connect-to-whatsapp)
- [🗄️ Implementing Data Store](#%EF%B8%8F-implementing-data-store)
- [🪪 WhatsApp IDs Explained](#-whatsapp-ids-explained)
- [✉️ Sending Messages](#%EF%B8%8F-sending-messages)
- [📁 Sending Media Messages](#-sending-media-messages)
- [👉🏻 Sending Interactive Messages](#-sending-interactive-messages)
- [💳 Sending Payment Messages](#-sending-payment-messages)
- [👁️ Other Message Options](#%EF%B8%8F-other-message-options)
- [♻️ Modify Messages](#%EF%B8%8F-modify-messages)
- [🧰 Additional Contents](#-additional-contents)
- [🚀 Try the Bot](#-try-the-bot)
- [📦 Fork Base](#-fork-base)
- [📣 Credits](#-credits)

</details>

---

## 🛠️ Internal Adjustments

| Fix | Description |
|-----|-------------|
| 🖼️ | Fixed newsletter media upload issue |
| 📁 | Reintroduced [`makeInMemoryStore`](#%EF%B8%8F-implementing-data-store) with ESM adaptation for Baileys v7 |
| 📦 | Switched FFmpeg from `exec` to `spawn` for safer process handling |
| 🗃️ | Added [`@napi-rs/image`](https://www.npmjs.com/package/@napi-rs/image) support in [`getImageProcessingLibrary()`](#%EF%B8%8F-image-processing) |

---

## 📨 Messages Handling & Compatibility

Expanded message support for:

| Category | Types |
|----------|-------|
| 🖼️ **Album** | [Album Message](#%EF%B8%8F-album-image--video) |
| 👤 **Group** | [Group Status Message](#%E2%80%8D%E2%80%8D-group-status) |
| 👉🏻 **Interactive** | [Buttons](#-buttons), [Lists](#-list), [Native Flows](#%EF%B8%8F-interactive), [Templates](#%EF%B8%8F-hydrated-template), [Carousels](#%EF%B8%8F-interactive) |
| 🎞️ **Status** | [Status Mention Message](#%EF%B8%8F-status-mention) |
| 📦 **Sticker** | [Sticker Pack Message](#-sticker-pack) |
| ✨ **Rich** | [Rich Response Message](#-rich-response) **[NEW]** |
| 🧾 **Code** | [Message with Code Blocks](#-message-with-code-block) **[NEW]** |
| 🌏 **Entities** | [Message with Inline Entities](#-message-with-inline-entities) **[NEW]** |
| 📋 **Table** | [Message with Table](#-message-with-table) **[NEW]** |
| 💳 **Payment** | [Payment-related Messages](#-sending-payment-messages) |

### Additional Enhancements
- 📰 Simplified `externalAdReply` — no manual `contextInfo` required
- 💭 Quote messages inside channels/newsletters **[NEW]**
- 🎀 Custom button icon support in interactive messages **[NEW]**

---

## 🧩 Additional Message Options

Optional boolean flags for message handling:

| Flag | Description |
|------|-------------|
| 🤖 `ai` | AI icon on message |
| 📣 `mentionAll` | Mention all group participants without JIDs **[NEW]** |
| 🔧 `ephemeral` | Disappearing messages |
| 👥 `groupStatus` | Group status message |
| 🐱 `isLottie` | Lottie sticker |
| 📑 `spoiler` | Spoiler message |
| 👁️ `viewOnce` / `viewOnceV2` / `viewOnceV2Extension` | View once messages |
| 🗄️ `interactiveAsTemplate` | Interactive as template |
| 🔒 `secureMetaServiceLabel` | Secure meta service label **[NEW]** |
| 📄 `raw` | Build messages manually |

---

## 📥 Installation

### Via `package.json`

```json
# NPM
"dependencies": {
  "@zavedyaid/baileys": "latest"
}

# GitHub
"dependencies": {
  "@zavedyaid/baileys": "github:zavedyaid/baileys"
}
```

Via Terminal

```bash
# NPM
npm i @zavedyaid/baileys@latest

# GitHub
npm i github:zavedyaid/baileys
```

Import (ESM & CJS)

```javascript
// --- ESM
import { makeWASocket } from '@zavedyaid/baileys'

// --- CJS (tested and working on Node.js 24 ✅)
const { makeWASocket } = require('@zavedyaid/baileys')
```

---

🌐 Connect to WhatsApp

```javascript
import { makeWASocket, delay, DisconnectReason, useMultiFileAuthState } from '@zavedyaid/baileys'
import { Boom } from '@hapi/boom'
import pino from 'pino'

const myPhoneNumber = '6288888888888'
const logger = pino({ level: 'silent' })

const connectToWhatsApp = async () => {
  const { state, saveCreds } = await useMultiFileAuthState('session')
  
  const sock = makeWASocket({
    logger,
    auth: state
  })

  sock.ev.on('creds.update', saveCreds)

  sock.ev.on('connection.update', async (update) => {
    const { connection, lastDisconnect } = update
    if (connection === 'connecting' && !sock.authState.creds.registered) {
      await delay(1500)
      const code = await sock.requestPairingCode(myPhoneNumber)
      console.log('🔗 Pairing code:', code)
    }
    else if (connection === 'close') {
      const shouldReconnect = new Boom(lastDisconnect?.error)?.output?.statusCode !== DisconnectReason.loggedOut
      console.log('⚠️ Connection closed, reconnecting:', shouldReconnect)
      if (shouldReconnect) connectToWhatsApp()
    }
    else if (connection === 'open') {
      console.log('✅ Successfully connected to WhatsApp')
    }
  })

  sock.ev.on('messages.upsert', async ({ messages }) => {
    for (const message of messages) {
      if (!message.message) continue
      console.log('🔔 New message:', message)
      await sock.sendMessage(message.key.remoteJid, {
        text: '👋🏻 Hello world'
      })
    }
  })
}

connectToWhatsApp()
```

🔐 Auth State

[!NOTE]
You can use useSingleFileAuthState and useSqliteAuthState as alternatives. useSingleFileAuthState already includes internal caching — no need to wrap with makeCacheableSignalKeyStore.

---

🗄️ Implementing Data Store

[!CAUTION]
I highly recommend building your own data store — keeping entire chat history in memory can lead to excessive RAM usage.

```javascript
import { makeWASocket, makeInMemoryStore, delay, DisconnectReason, useMultiFileAuthState } from '@zavedyaid/baileys'
import { Boom } from '@hapi/boom'
import pino from 'pino'

const myPhoneNumber = '6288888888888'
const storePath = './store.json'
const logger = pino({ level: 'silent' })

const connectToWhatsApp = async () => {
  const { state, saveCreds } = await useMultiFileAuthState('session')
  
  const sock = makeWASocket({
    logger,
    auth: state
  })

  const store = makeInMemoryStore({
    logger,
    socket: sock
  })
  store.bind(sock.ev)

  sock.ev.on('creds.update', saveCreds)

  sock.ev.on('connection.update', async (update) => {
    const { connection, lastDisconnect } = update
    if (connection === 'connecting' && !sock.authState.creds.registered) {
      await delay(1500)
      const code = await sock.requestPairingCode(myPhoneNumber)
      console.log('🔗 Pairing code:', code)
    }
    else if (connection === 'close') {
      const shouldReconnect = new Boom(lastDisconnect?.error)?.output?.statusCode !== DisconnectReason.loggedOut
      console.log('⚠️ Connection closed, reconnecting:', shouldReconnect)
      if (shouldReconnect) connectToWhatsApp()
    }
    else if (connection === 'open') {
      console.log('✅ Successfully connected to WhatsApp')
    }
  })

  sock.ev.on('chats.upsert', () => {
    console.log('✉️ Chats:', store.chats.all())
  })

  sock.ev.on('contacts.upsert', () => {
    console.log('👥 Contacts:', Object.values(store.contacts))
  })

  store.readFromFile(storePath)
  setInterval(() => store.writeToFile(storePath), 180000)
}

connectToWhatsApp()
```

---

🪪 WhatsApp IDs Explained

id (also called jid or lid) is the WhatsApp identifier:

Type Format Example
Person [country][number]@s.whatsapp.net 19999999999@s.whatsapp.net
Person (LID) [number]@lid 12699999999@lid
Group [id]@g.us 123456789-123345@g.us
Meta AI 11111111111@bot —
Broadcast [timestamp]@broadcast —
Stories status@broadcast —

---

✉️ Sending Messages

[!NOTE]
Get jid from message.key.remoteJid in the message event.

🔠 Text

```javascript
// Regular text
sock.sendMessage(jid, {
  text: '👋🏻 Hello'
}, { quoted: message })

// Text with link preview
const url = 'https://www.npmjs.com/package/@zavedyaid/baileys'
sock.sendMessage(jid, {
  text: url + ' 👆🏻 Check it out!',
  linkPreview: {
    'matched-text': url,
    title: '🌱 @zavedyaid/baileys',
    description: 'Underrated Baileys Fork',
    previewType: 0, // 0 = image, 1 = video
    jpegThumbnail: fs.readFileSync('./path/to/image.jpg')
  }
})

// Text with large link preview
import { prepareWAMessageMedia } from '@zavedyaid/baileys'

const { imageMessage: image } = await prepareWAMessageMedia({
  image: { url: './path/to/image.jpg' }
}, {
  upload: sock.waUploadToServer,
  mediaTypeOverride: 'thumbnail-link'
})

sock.sendMessage(jid, {
  text: url + ' 👆🏻 Check it out!',
  linkPreview: {
    'matched-text': url,
    title: '🌱 @zavedyaid/baileys',
    description: 'Underrated Baileys Fork',
    previewType: 0,
    jpegThumbnail: fs.readFileSync('./path/to/image.jpg'),
    highQualityThumbnail: image,
    linkPreviewMetadata: {
      linkMediaDuration: 0,
      socialMediaPostType: 1 // 0=NONE, 1=REEL, 2=LIVE_VIDEO, 3=LONG_VIDEO, 4=SINGLE_IMAGE, 5=CAROUSEL
    }
  },
  favicon: { url: './path/to/tiny-image.ico' }
})
```

🔔 Mention

```javascript
// Regular mention
sock.sendMessage(jid, {
  text: '👋🏻 Hello @628123456789',
  mentions: ['628123456789@s.whatsapp.net']
}, { quoted: message })

// Mention all
sock.sendMessage(jid, {
  text: '👋🏻 Hello @all',
  mentionAll: true
}, { quoted: message })
```

😁 Reaction

```javascript
sock.sendMessage(jid, {
  react: {
    key: message.key,
    text: '✨'
  }
})
```

📌 Pin Message

```javascript
sock.sendMessage(jid, {
  pin: message.key,
  time: 86400, // 1d, 604800 (7d), or 2592000 (30d)
  type: 1 // 1 = pin, 2 = unpin
})
```

🔖 Keep Chat

[!NOTE]
Keep Chat only works in chats/groups with disappearing messages enabled.

```javascript
sock.sendMessage(jid, {
  keep: message.key,
  type: 1 // 1 = keep, 2 = remove
})
```

➡️ Forward Message

```javascript
sock.sendMessage(jid, {
  forward: message,
  force: true // Optional
})
```

👤 Contact

```javascript
const vcard = 'BEGIN:VCARD\nVERSION:3.0\nFN:Lia Wynn\nORG:Waitress;\nTEL;type=CELL;type=VOICE;waid=628123456789:+62 8123 4567 89\nEND:VCARD'

sock.sendMessage(jid, {
  contacts: {
    displayName: 'Lia Wynn',
    contacts: [{ vcard }]
  }
}, { quoted: message })
```

📍 Location

```javascript
sock.sendMessage(jid, {
  location: {
    degreesLatitude: 24.121231,
    degreesLongitude: 55.1121221,
    name: '👋🏻 I am here'
  }
}, { quoted: message })
```

🗓️ Event

```javascript
sock.sendMessage(jid, {
  event: {
    name: '🎶 Meet & Mingle Party',
    description: 'Meet & Mingle Party is a fun, casual gathering...',
    call: 'audio', // or 'video'
    startDate: new Date(Date.now() + 3600000),
    endDate: new Date(Date.now() + 28800000),
    isCancelled: false,
    isScheduleCall: false,
    extraGuestsAllowed: false,
    location: {
      name: 'Jakarta',
      degreesLatitude: -6.2,
      degreesLongitude: 106.8
    }
  }
}, { quoted: message })
```

👥 Group Invite

```javascript
const inviteCode = groupUrl.split('chat.whatsapp.com/')[1]?.split('?')[0]

sock.sendMessage(jid, {
  groupInvite: {
    inviteCode,
    inviteExpiration: Date.now() + 86400000,
    text: '👋🏻 Hello, we invite you to join our group.',
    jid: '1201111111111@g.us',
    subject: '@zavedyaid/baileys'
  }
}, { quoted: message })
```

🛍️ Product

```javascript
import { randomUUID } from 'crypto'

sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  body: '👋🏻 Check my product here!',
  footer: '@zavedyaid/baileys',
  product: {
    currencyCode: 'IDR',
    description: '🛍️ Interesting product!',
    priceAmount1000: 70_000_000,
    productId: randomUUID(),
    productImageCount: 1,
    salePriceAmount1000: 65_000_000,
    signedUrl: 'https://www.npmjs.com/package/@zavedyaid/baileys',
    title: '📦 Starseed (Premium)',
    url: 'https://www.npmjs.com/package/@zavedyaid/baileys'
  },
  businessOwnerJid: '0@s.whatsapp.net'
})
```

📊 Poll

```javascript
// Regular poll
sock.sendMessage(jid, {
  poll: {
    name: '🔥 Voting time',
    values: ['Yes', 'No'],
    selectableCount: 1,
    toAnnouncementGroup: false,
    endDate: new Date(Date.now() + 28800000),
    hideVoter: false,
    canAddOption: false
  }
}, { quoted: message })

// Quiz (newsletter only)
sock.sendMessage('1211111111111@newsletter', {
  poll: {
    name: '🔥 Quiz',
    values: ['Yes', 'No'],
    correctAnswer: 'Yes',
    pollType: 1
  }
}, { quoted: message })

// Poll result
sock.sendMessage(jid, {
  pollResult: {
    name: '📝 Poll Result',
    votes: [
      { name: 'Nice', voteCount: 10 },
      { name: 'Nah', voteCount: 2 }
    ],
    pollType: 0 // 0 = poll, 1 = quiz
  }
}, { quoted: message })
```

💭 Button Response

```javascript
// Using buttonsResponseMessage
sock.sendMessage(jid, {
  type: 'plain',
  buttonReply: {
    id: '#Menu',
    displayText: '✨ Interesting Menu'
  }
}, { quoted: message })

// Using interactiveResponseMessage
sock.sendMessage(jid, {
  flowReply: {
    format: 0,
    text: '💭 Response',
    name: 'menu_options',
    paramsJson: JSON.stringify({
      id: '#Menu',
      description: '✨ Interesting Menu'
    })
  }
}, { quoted: message })

// Using listResponseMessage
sock.sendMessage(jid, {
  listReply: {
    title: '📄 See More',
    description: '✨ Interesting Menu',
    id: '#Menu'
  }
}, { quoted: message })
```

✨ Rich Response

```javascript
sock.sendMessage(jid, {
  disclaimerText: 'RAW submessages structure example',
  richResponse: [
    { text: 'Example Usage' },
    {
      language: 'javascript',
      code: [{ highlightType: 0, codeContent: 'console.log("Hello, World!")' }]
    },
    { text: 'Pretty simple, right?\n' },
    { text: 'Comparison between Node.js, Bun, and Deno' },
    {
      title: 'Runtime Comparison',
      table: [
        { isHeading: true, items: ['', 'Node.js', 'Bun', 'Deno'] },
        { isHeading: false, items: ['Engine', 'V8 (C++)', 'JavaScriptCore (C++)', 'V8 (C++)'] },
        { isHeading: false, items: ['Performance', '4/5', '5/5', '4/5'] }
      ]
    },
    { text: 'Does this help clarify the differences?' }
  ]
})
```

💡 Tip: Use tokenizeCode for syntax highlighting:

```javascript
import { tokenizeCode } from '@zavedyaid/baileys'

const language = 'javascript'
const code = 'console.log("Hello, World!")'

sock.sendMessage(jid, {
  disclaimerText: 'Example of tokenizing Code Block',
  richResponse: [
    { text: 'Example Usage' },
    { language, code: tokenizeCode(code, language) },
    { text: 'Pretty simple, right?' }
  ]
})
```

💡 Supported Languages: css, html, javascript, typescript, python, golang, rust, c, c#, c++, bash, bat, powershell

🧾 Message with Code Block

```javascript
sock.sendMessage(jid, {
  disclaimerText: 'Code Block',
  headerText: '## Example Usage',
  contentText: '---',
  code: 'console.log("Hello, World!")',
  language: 'javascript',
  footerText: 'Pretty simple, right?'
})
```

🌏 Message with Inline Entities

```javascript
sock.sendMessage(jid, {
  disclaimerText: 'Inline Entities',
  headerText: '## Check Out!',
  contentText: '---',
  links: [
    { text: '1. Google', title: 'Popular Search Engine', url: 'https://www.google.com/' },
    { text: '2. YouTube', title: 'Popular Streaming Platform', url: 'https://www.youtube.com/' },
    { text: '3. Modded Baileys', title: 'Underrated Baileys Fork', url: 'https://www.npmjs.com/package/@zavedyaid/baileys' }
  ],
  footerText: '---'
})
```

📋 Message with Table

```javascript
sock.sendMessage(jid, {
  disclaimerText: 'Table',
  headerText: '## Comparison between Node.js, Bun, and Deno',
  contentText: '---',
  title: 'Runtime Comparison',
  table: [
    ['', 'Node.js', 'Bun', 'Deno'],
    ['Engine', 'V8 (C++)', 'JavaScriptCore (C++)', 'V8 (C++)'],
    ['Performance', '4/5', '5/5', '4/5']
  ],
  noHeading: false,
  footerText: 'Does this help clarify the differences?'
})
```

🎞️ Status Mention

```javascript
sock.sendMessage([jidA, jidB, jidC], {
  text: 'Hello! 👋🏻'
})
```

---

📁 Sending Media Messages

[!NOTE]
Media can be a Buffer, { stream: Readable }, or { url: string } (local file or HTTP/HTTPS URL).

🖼️ Image

```javascript
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '🔥 Superb'
}, { quoted: message })
```

🎥 Video

```javascript
sock.sendMessage(jid, {
  video: { url: './path/to/video.mp4' },
  gifPlayback: false, // true = send as GIF
  ptv: false, // true = send as PTV
  caption: '🔥 Superb'
}, { quoted: message })
```

📃 Sticker

```javascript
sock.sendMessage(jid, {
  sticker: { url: './path/to/sticker.webp' }
}, { quoted: message })
```

💽 Audio

```javascript
sock.sendMessage(jid, {
  audio: { url: './path/to/audio.mp3' },
  ptt: false // true = send as Voice Note
}, { quoted: message })
```

🗂️ Document

```javascript
sock.sendMessage(jid, {
  document: { url: './path/to/document.pdf' },
  mimetype: 'application/pdf',
  caption: '✨ My work!'
}, { quoted: message })
```

🖼️ Album (Image & Video)

```javascript
sock.sendMessage(jid, {
  album: [
    { image: { url: './path/to/image.jpg' }, caption: '1st image' },
    { video: { url: './path/to/video.mp4' }, caption: '1st video' },
    { image: { url: './path/to/image.jpg' }, caption: '2nd image' },
    { video: { url: './path/to/video.mp4' }, caption: '2nd video' }
  ]
}, { quoted: message })
```

📦 Sticker Pack

[!IMPORTANT]
If sharp or @napi-rs/image is not installed, cover and stickers must already be in WebP format.

```javascript
sock.sendMessage(jid, {
  cover: { url: './path/to/image.webp' },
  stickers: [
    { data: { url: './path/to/image.webp' } },
    { data: { url: './path/to/image.webp' } },
    { data: { url: './path/to/image.webp' } }
  ],
  name: '📦 My Sticker Pack',
  publisher: '🌟 Lia Wynn',
  description: '@zavedyaid/baileys'
}, { quoted: message })
```

---

👉🏻 Sending Interactive Messages

🔘 Buttons

```javascript
// Regular buttons
sock.sendMessage(jid, {
  text: '👆🏻 Buttons!',
  footer: '@zavedyaid/baileys',
  buttons: [{ text: '👋🏻 SignUp', id: '#SignUp' }]
}, { quoted: message })

// Buttons with Media & Native Flow
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '👆🏻 Buttons and Native Flow!',
  footer: '@zavedyaid/baileys',
  buttons: [
    { text: '👋🏻 Rating', id: '#Rating' },
    {
      text: '📋 Select',
      sections: [{
        title: '✨ Section 1',
        rows: [{ header: '', title: '💭 Secret Ingredient', description: '', id: '#SecretIngredient' }]
      }, {
        title: '✨ Section 2',
        highlight_label: '🔥 Popular',
        rows: [{ header: '', title: '🏷️ Coupon', description: '', id: '#CouponCode' }]
      }]
    }
  ]
}, { quoted: message })
```

📋 List

[!NOTE]
Only works in private chat (@s.whatsapp.net).

```javascript
sock.sendMessage(jid, {
  text: '📋 List!',
  footer: '@zavedyaid/baileys',
  buttonText: '📋 Select',
  title: '👋🏻 Hello',
  sections: [
    {
      title: '🚀 Menu 1',
      rows: [{ title: '✨ AI', description: '', rowId: '#AI' }]
    },
    {
      title: '🌱 Menu 2',
      rows: [{ title: '🔍 Search', description: '', rowId: '#Search' }]
    }
  ]
}, { quoted: message })
```

🗄️ Interactive

```javascript
// Native Flow
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '🗄️ Interactive!',
  footer: '@zavedyaid/baileys',
  optionText: '👉🏻 Select Options',
  optionTitle: '📄 Select Options',
  offerText: '🏷️ Newest Coupon!',
  offerCode: '@zavedyaid/baileys',
  offerUrl: 'https://www.npmjs.com/package/@zavedyaid/baileys',
  offerExpiration: Date.now() + 3_600_000,
  nativeFlow: [
    { text: '👋🏻 Greeting', id: '#Greeting', icon: 'review' },
    { text: '📞 Call', call: '628123456789' },
    { text: '📋 Copy', copy: '@zavedyaid/baileys' },
    { text: '🌐 Source', url: 'https://www.npmjs.com/package/@zavedyaid/baileys', useWebview: true },
    {
      text: '📋 Select',
      sections: [
        {
          title: '✨ Section 1',
          rows: [{ header: '', title: '🏷️ Coupon', description: '', id: '#CouponCode' }]
        },
        {
          title: '✨ Section 2',
          highlight_label: '🔥 Popular',
          rows: [{ header: '', title: '💭 Secret Ingredient', description: '', id: '#SecretIngredient' }]
        }
      ],
      icon: 'default'
    }
  ],
  interactiveAsTemplate: false
}, { quoted: message })

// Carousel & Native Flow
sock.sendMessage(jid, {
  text: '🗂️ Interactive with Carousel!',
  footer: '@zavedyaid/baileys',
  cards: [
    {
      image: { url: './path/to/image.jpg' },
      caption: '🖼️ Image 1',
      footer: '🏷️ Pinterest',
      nativeFlow: [{ text: '🌐 Source', url: 'https://www.npmjs.com/package/@zavedyaid/baileys', useWebview: true }]
    },
    {
      image: { url: './path/to/image.jpg' },
      caption: '🖼️ Image 2',
      footer: '🏷️ Pinterest',
      offerText: '🏷️ New Coupon!',
      offerCode: '@zavedyaid/baileys',
      offerUrl: 'https://www.npmjs.com/package/@zavedyaid/baileys',
      offerExpiration: Date.now() + 3_600_000,
      nativeFlow: [{ text: '🌐 Source', url: 'https://www.npmjs.com/package/@zavedyaid/baileys' }]
    },
    {
      image: { url: './path/to/image.jpg' },
      caption: '🖼️ Image 3',
      footer: '🏷️ Pinterest',
      optionText: '👉🏻 Select Options',
      optionTitle: '👉🏻 Select Options',
      offerText: '🏷️ New Coupon!',
      offerCode: '@zavedyaid/baileys',
      offerUrl: 'https://www.npmjs.com/package/@zavedyaid/baileys',
      offerExpiration: Date.now() + 3_600_000,
      nativeFlow: [
        { text: '🛒 Product', id: '#Product', icon: 'default' },
        { text: '🌐 Source', url: 'https://www.npmjs.com/package/@zavedyaid/baileys' }
      ]
    }
  ]
}, { quoted: message })

// Native Flow with Audio in Footer
sock.sendMessage(jid, {
  text: '🔈 Music in the footer!',
  audioFooter: { url: './path/to/audio.mp3' },
  nativeFlow: [
    { text: '👍🏻 Good, next', id: '#Next', icon: 'review' },
    { text: '👎🏻 Skip', id: '#Skip', icon: 'default' }
  ]
}, { quoted: message })
```

🫙 Hydrated Template

```javascript
sock.sendMessage(jid, {
  title: '👋🏻 Hello',
  image: { url: './path/to/image.jpg' },
  caption: '🫙 Template!',
  footer: '@zavedyaid/baileys',
  templateButtons: [
    { text: '👉🏻 Tap Here', id: '#Order' },
    { text: '🌐 Source', url: 'https://www.npmjs.com/package/@zavedyaid/baileys' },
    { text: '📞 Call', call: '628123456789' }
  ]
}, { quoted: message })
```

---

💳 Sending Payment Messages

➕ Invite Payment

```javascript
sock.sendMessage(jid, {
  paymentInviteServiceType: 3 // 1, 2, or 3
})
```

🧾 Invoice

```javascript
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  invoiceNote: '🏷️ Invoice'
})
```

🛍️ Order

```javascript
sock.sendMessage(chat, {
  orderText: '🛍️ Order',
  thumbnail: fs.readFileSync('./path/to/image.jpg')
}, { quoted: message })
```

💳 Request Payment

```javascript
sock.sendMessage(jid, {
  text: '💳 Request Payment',
  requestPaymentFrom: '0@s.whatsapp.net'
})
```

---

👁️ Other Message Options

🤖 AI Icon

[!NOTE]
Only works in private chat (@s.whatsapp.net).

```javascript
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '🤖 With AI icon!',
  ai: true
}, { quoted: message })
```

🕒 Ephemeral

```javascript
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '👁️ Ephemeral',
  ephemeral: true
})
```

📰 External Ad Reply

```javascript
sock.sendMessage(jid, {
  text: '📰 External Ad Reply',
  externalAdReply: {
    title: '📝 Did you know?',
    body: '❓ I dont know',
    thumbnail: fs.readFileSync('./path/to/image.jpg'),
    largeThumbnail: false,
    url: 'https://www.npmjs.com/package/@zavedyaid/baileys'
  }
}, { quoted: message })
```

🧑‍🧑‍🧒 Group Status

[!NOTE]
Only works in group chat (@g.us).

```javascript
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '👥 Group Status!',
  groupStatus: true
})
```

🐱 Lottie Sticker

```javascript
sock.sendMessage(jid, {
  sticker: { url: './path/to/sticker.webp' },
  isLottie: true
})
```

🧩 Raw

```javascript
sock.sendMessage(jid, {
  extendedTextMessage: {
    text: '📃 Built manually from scratch using the raw WhatsApp proto structure',
    contextInfo: {
      externalAdReply: {
        title: '@zavedyaid/baileys',
        thumbnail: fs.readFileSync('./path/to/image.jpg'),
        sourceApp: 'whatsapp',
        showAdAttribution: true,
        mediaType: 1
      }
    }
  },
  raw: true
}, { quoted: message })
```

🏷️ Secure Meta Service Label

```javascript
sock.sendMessage(jid, {
  text: '🏷️ Just a label!',
  secureMetaServiceLabel: true
})
```

📑 Spoiler

```javascript
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '❔ Spoiler',
  spoiler: true
})
```

👁️ View Once

```javascript
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '👁️ View Once',
  viewOnce: true
})

// View Once V2
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '👁️ View Once V2',
  viewOnceV2: true
})

// View Once V2 Extension
sock.sendMessage(jid, {
  image: { url: './path/to/image.jpg' },
  caption: '👁️ View Once V2 Extension',
  viewOnceV2Extension: true
})
```

---

♻️ Modify Messages

🗑️ Delete Messages

```javascript
sock.sendMessage(jid, {
  delete: message.key
})
```

✏️ Edit Messages

```javascript
// Edit plain text
sock.sendMessage(jid, {
  text: '✨ I mean, nice!',
  edit: message.key
})

// Edit media caption
sock.sendMessage(jid, {
  caption: '✨ I mean, here is the image!',
  edit: message.key
})
```

---

🧰 Additional Contents

🏷️ Find User ID (JID/PN/LID)

```javascript
// PN (Phone Number)
const ids = await sock.findUserId('6281111111111@s.whatsapp.net')

// LID (Local Identifier)
const ids = await sock.findUserId('43411111111111@lid')

console.log('🏷️ Got user ID:', ids)
// Output: { phoneNumber: '6281111111111@s.whatsapp.net', lid: '43411111111111@lid' }
```

🔑 Request Custom Pairing Code

```javascript
const phoneNumber = '6281111111111'
const customPairingCode = 'STARFALL'

await sock.requestPairingCode(phoneNumber, customPairingCode)
console.log('🔗 Pairing code:', customPairingCode)
```

🖼️ Image Processing

```javascript
import { getImageProcessingLibrary } from '@zavedyaid/baileys'
import { readFile } from 'fs/promises'

const lib = await getImageProcessingLibrary()
const bufferOrFilePath = './path/to/image.jpg'
const width = 512
let output

if (lib.sharp?.default) {
  const img = lib.sharp.default(bufferOrFilePath)
  output = await img.resize(width).jpeg({ quality: 80 }).toBuffer()
} else if (lib.image?.Transformer) {
  const inputBuffer = Buffer.isBuffer(bufferOrFilePath) ? bufferOrFilePath : await readFile(bufferOrFilePath)
  const img = new lib.image.Transformer(inputBuffer)
  output = await img.resize(width, undefined, 0).jpeg(50)
} else if (lib.jimp?.Jimp) {
  const img = await lib.jimp.Jimp.read(bufferOrFilePath)
  output = await img.resize({ w: width, mode: lib.jimp.ResizeStrategy.BILINEAR })
    .getBuffer('image/jpeg', { quality: 50 })
} else {
  throw new Error('No image processing available')
}

console.log('✅ Process completed!')
console.dir(output, { depth: null })
```

📣 Newsletter Management

```javascript
// Create a new one
sock.newsletterCreate('@zavedyaid/baileys', '📣 Fresh updates weekly')

// Get info
const metadata = sock.newsletterMetadata('1231111111111@newsletter')
console.dir(metadata, { depth: null })

// Get subscribers count
const subscribers = await sock.newsletterSubscribers('1231111111111@newsletter')
console.dir(subscribers, { depth: null })

// Follow and Unfollow
sock.newsletterFollow('1231111111111@newsletter')
sock.newsletterUnfollow('1231111111111@newsletter')

// Mute and Unmute
sock.newsletterMute('1231111111111@newsletter')
sock.newsletterUnmute('1231111111111@newsletter')

// Demote admin
sock.newsletterDemote('1231111111111@newsletter', '6281111111111@s.whatsapp.net')

// Change owner
sock.newsletterChangeOwner('1231111111111@newsletter', '6281111111111@s.whatsapp.net')

// Update newsletter
sock.newsletterUpdate('1231111111111@newsletter', { name: '@zavedyaid/baileys' })

// Change name
sock.newsletterUpdateName('1231111111111@newsletter', '📦 @zavedyaid/baileys')

// Change description
sock.newsletterUpdateDescription('1231111111111@newsletter', '📣 Fresh updates weekly')

// Change photo
sock.newsletterUpdatePicture('1231111111111@newsletter', { url: 'path/to/image.jpg' })

// Remove photo
sock.newsletterRemovePicture('1231111111111@newsletter')

// React to a message
sock.newsletterReactMessage('1231111111111@newsletter', '100', '💛')

// Get admin count
const count = await sock.newsletterAdminCount('1231111111111@newsletter')

// Get all subscribed newsletters
const newsletters = await sock.newsletterSubscribed()
console.dir(newsletters, { depth: null })

// Fetch newsletter messages
const messages = sock.newsletterFetchMessages('jid', '1231111111111@newsletter', 50, 0, 0)
console.dir(messages, { depth: null })

// Delete newsletter
sock.newsletterDelete('1231111111111@newsletter')
```

👥 Group Management

```javascript
// Create a new one and add participants using their JIDs
const group = sock.groupCreate('@zavedyaid/baileys', ['628123456789@s.whatsapp.net'])
console.dir(group, { depth: null })

// Get info
const metadata = await sock.groupMetadata(jid)
console.dir(metadata, { depth: null })

// Get group invite code
const inviteCode = await sock.groupInviteCode(jid)
console.dir(inviteCode, { depth: null })

// Revoke invite link
sock.groupRevokeInvite(jid)

// Accept group invite
sock.groupAcceptInvite(inviteCode)

// Leave group
sock.groupLeave(jid)

// Add participants
sock.groupParticipantsUpdate(jid, ['628123456789@s.whatsapp.net'], 'add')

// Remove participants
sock.groupParticipantsUpdate(jid, ['628123456789@s.whatsapp.net'], 'remove')

// Promote to admin
sock.groupParticipantsUpdate(jid, ['628123456789@s.whatsapp.net'], 'promote')

// Demote from admin
sock.groupParticipantsUpdate(jid, ['628123456789@s.whatsapp.net'], 'demote')

// Accept join requests
sock.groupRequestParticipantsUpdate(jid, ['628123456789@s.whatsapp.net'], 'approve')

// Change name
sock.groupUpdateSubject(jid, '📦 @zavedyaid/baileys')

// Change description
sock.groupUpdateDescription(jid, 'Updated description')

// Change photo
sock.updateProfilePicture(jid, { url: 'path/to/image.jpg' })

// Remove photo
sock.removeProfilePicture(jid)

// Set group as admin only for chatting
sock.groupSettingUpdate(jid, 'announcement')
sock.groupSettingUpdate(jid, 'not_announcement')

// Set admin only can edit group info
sock.groupSettingUpdate(jid, 'locked')
sock.groupSettingUpdate(jid, 'unlocked')

// Set admin only can add participants
sock.groupMemberAddMode(jid, 'admin_add')
sock.groupMemberAddMode(jid, 'all_member_add')

// Enable or disable temporary messages with seconds format
sock.groupToggleEphemeral(jid, 86400)
sock.groupToggleEphemeral(jid, 0)

// Enable or disable membership approval mode
sock.groupJoinApprovalMode(jid, 'on')
sock.groupJoinApprovalMode(jid, 'off')

// Get all groups metadata
const groups = await sock.groupFetchAllParticipating()
console.dir(groups, { depth: null })

// Get pending join requests
const requests = await sock.groupRequestParticipantsList(jid)
console.dir(requests, { depth: null })

// Get group info from link
const groupInfo = await sock.groupGetInviteInfo('ABC123456789')
console.log('👥 Got group info from invite code:', groupInfo)

// Update bot member label
sock.updateMemberLabel(jid, '@zavedyaid/baileys')
```

👥 Community Management

```javascript
// Create a new one and add description
const community = await sock.communityCreate('@zavedyaid/baileys', '📣 Fresh updates weekly')
console.dir(community, { depth: null })

// Create a subgroup for community
const group = await sock.communityCreateGroup('📢 Announcements', ['628123456789@s.whatsapp.net'], communityJid)

// Link an existing group
sock.communityLinkGroup(groupJid, communityJid)

// Unlink an existing group
sock.communityUnlinkGroup(groupJid, communityJid)

// Get info
const metadata = await sock.communityMetadata(jid)
console.dir(metadata, { depth: null })

// Get community invite code
const inviteCode = await sock.communityInviteCode(jid)
console.dir(inviteCode, { depth: null })

// Revoke invite link
sock.communityRevokeInvite(jid)

// Accept community invite
sock.communityAcceptInvite(inviteCode)

// Leave community
sock.communityLeave(jid)

// Accept join requests
sock.communityRequestParticipantsUpdate(jid, ['628123456789@s.whatsapp.net'], 'approve')

// Change name
sock.communityUpdateSubject(jid, '📦 @zavedyaid/baileys')

// Change description
sock.communityUpdateDescription(jid, 'Updated description')

// Set community as admin only for chatting
sock.communitySettingUpdate(jid, 'announcement')
sock.communitySettingUpdate(jid, 'not_announcement')

// Set admin only can edit community info
sock.communitySettingUpdate(jid, 'locked')
sock.communitySettingUpdate(jid, 'unlocked')

// Set admin only can add participants
sock.communityMemberAddMode(jid, 'admin_add')
sock.communityMemberAddMode(jid, 'all_member_add')

// Enable or disable temporary messages
sock.communityToggleEphemeral(jid, 86400)
sock.communityToggleEphemeral(jid, 0)

// Enable or disable membership approval mode
sock.communityJoinApprovalMode(jid, 'on')
sock.communityJoinApprovalMode(jid, 'off')

// Get all communities metadata
const communities = await sock.communityFetchAllParticipating()
console.dir(communities, { depth: null })

// Get all community linked groups
const linked = await sock.communityFetchLinkedGroups(jid)
console.dir(linked, { depth: null })

// Get pending join requests
const requests = await sock.communityRequestParticipantsList(jid)
console.dir(requests, { depth: null })

// Get community info from link
const communityInfo = await sock.communityGetInviteInfo('ABC123456789')
console.log('👥 Got community info from invite code:', communityInfo)
```

👤 Profile Management

```javascript
// Get user profile picture
const url = await sock.profilePictureUrl(jid, 'image')
console.log('🖼️ Got user profile url:', url)

// Update profile picture
sock.updateProfilePicture(jid, buffer)
sock.updateProfilePicture(jid, { url })

// Remove profile picture
sock.removeProfilePicture(jid)

// Update profile name
sock.updateProfileName('My Name')

// Update profile status
sock.updateProfileStatus('Available')

// Presence
sock.sendPresenceUpdate('available', jid)
sock.presenceSubscribe(jid)

// Read receipts
sock.readMessages([message.key])
sock.sendReceipt(jid, participant, [messageId], 'read')

// Block user
sock.updateBlockStatus(jid, 'block')
sock.updateBlockStatus(jid, 'unblock')

// Fetch blocklist
const blocked = await sock.fetchBlocklist()
console.dir(blocked, { depth: null })

// Modify chats
sock.chatModify({
  archive: true,
  lastMessageOrig: message,
  lastMessage: message
}, jid)

// Star messages
sock.star(jid, [{ id: messageId, fromMe: true }], true)

// Contact
sock.addOrEditContact(jid, { displayName: 'Starseed' })
sock.removeContact(jid)

// Label
sock.addChatLabel(jid, labelId)
sock.removeChatLabel(jid, labelId)
sock.addMessageLabel(jid, messageId, labelId)

// App state sync
sock.resyncAppState(['regular', 'critical_block'], true)

// Get business profile
const profile = await sock.getBusinessProfile(jid)
console.dir(profile, { depth: null })
```

🛒 Business Management

```javascript
// Create a new product
const product = await sock.productCreate({
  name: '🧩 Starseed (Premium)',
  description: 'Get a full version of Starseed!',
  price: 100000,
  currency: 'IDR',
  originCountryCode: 'ID',
  images: [
    bufferImage,
    { url: './path/to/image.jpg' }
  ]
})
console.dir(product, { depth: null })

// Update product
await sock.productUpdate(productId, {
  name: '🧩 Starseed (Premium)',
  description: 'Get a full version of Starseed with more features!',
  price: 75000,
  currency: 'IDR',
  images: [{ url: './path/to/image.jpg' }]
})

// Delete product
sock.productDelete([productId])

// Get catalog info
const { products, nextPageCursor } = await sock.getCatalog({
  jid: '628123456789@s.whatsapp.net',
  limit: 10
})

// Get collections
const collections = await sock.getCollections('628123456789@s.whatsapp.net', 10)
console.dir(collections, { depth: null })

// Get order info
const order = await sock.getOrderDetails(orderId, tokenBase64)
console.dir(order, { depth: null })

// Update business profile
await sock.updateBusinessProfile({
  address: 'Jakarta, Indonesia',
  description: '🛒 Official Starseed Store',
  websites: ['https://www.npmjs.com/package/@zavedyaid/baileys'],
  email: 'more-more@gmail.com',
  hours: {
    timezone: 'Asia/Jakarta',
    days: [{ day: 'mon', mode: 'open_24h' }]
  }
})

// Update cover
sock.updateCoverPhoto({ url: './path/to/image.jpg' })

// Remove cover
sock.removeCoverPhoto(coverId)

// Update quick replies
sock.addOrEditQuickReply({
  shortcut: 'hello',
  message: 'Hello from business account',
})

// Remove quick reply
sock.removeQuickReply(timestamp)
```

🔐 Privacy Management

```javascript
// Update last seen privacy
sock.updateLastSeenPrivacy('all')
sock.updateLastSeenPrivacy('contacts')
sock.updateLastSeenPrivacy('contact_blacklist')
sock.updateLastSeenPrivacy('nobody')

// Update online privacy
sock.updateOnlinePrivacy('all')
sock.updateOnlinePrivacy('match_last_seen')

// Update profile picture privacy
sock.updateProfilePicturePrivacy('contacts')

// Update status privacy
sock.updateStatusPrivacy('contacts')

// Update read receipts privacy
sock.updateReadReceiptsPrivacy('all')
sock.updateReadReceiptsPrivacy('none')

// Update groups add privacy
sock.updateGroupsAddPrivacy('all')
sock.updateGroupsAddPrivacy('contacts')

// Update messages privacy
sock.updateMessagesPrivacy('all')
sock.updateMessagesPrivacy('contacts')
sock.updateMessagesPrivacy('nobody')

// Update call privacy
sock.updateCallPrivacy('everyone')

// Update default disappearing mode
sock.updateDefaultDisappearingMode(86400)

// Update link previews privacy
sock.updateDisableLinkPreviewsPrivacy(true)
```

📡 Events

```javascript
sock.ev.on('connection.update', (update) => {})
sock.ev.on('creds.update', (update) => {})
sock.ev.on('messaging-history.set', (update) => {})
sock.ev.on('messaging-history.status', (update) => {})
sock.ev.on('chats.upsert', (update) => {})
sock.ev.on('chats.update', (update) => {})
sock.ev.on('chats.delete', (update) => {})
sock.ev.on('chats.lock', (update) => {})
sock.ev.on('lid-mapping.update', (update) => {})
sock.ev.on('presence.update', (update) => {})
sock.ev.on('contacts.upsert', (update) => {})
sock.ev.on('contacts.update', (update) => {})
sock.ev.on('messages.delete', (update) => {})
sock.ev.on('messages.update', (update) => {})
sock.ev.on('messages.media-update', (update) => {})
sock.ev.on('messages.upsert', (update) => {})
sock.ev.on('messages.reaction', (update) => {})
sock.ev.on('message-receipt.update', (update) => {})
sock.ev.on('groups.upsert', (update) => {})
sock.ev.on('groups.update', (update) => {})
sock.ev.on('group-participants.update', (update) => {})
sock.ev.on('group.join-request', (update) => {})
sock.ev.on('group.member-tag.update', (update) => {})
sock.ev.on('blocklist.set', (update) => {})
sock.ev.on('blocklist.update', (update) => {})
sock.ev.on('call', (update) => {})
sock.ev.on('labels.edit', (update) => {})
sock.ev.on('labels.association', (update) => {})
sock.ev.on('newsletter.reaction', (update) => {})
sock.ev.on('newsletter.view', (update) => {})
sock.ev.on('newsletter-participants.update', (update) => {})
sock.ev.on('newsletter-settings.update', (update) => {})
sock.ev.on('settings.update', (update) => {})
```

---

🚀 Try the Bot

A fast, lightweight, and modular WhatsApp bot built with @zavedyaid/baileys. Perfect for managing groups, moderating chats, and adding fun with quiz games and handy tools.

👉🏻 @zavedyaid/starseed

A lightweight yet powerful Baileys wrapper designed to simplify development while extending support for additional message types and WhatsApp features.

👉🏻 @zavedyaid/starcore

---

📦 Fork Base

This fork is based on Baileys (GitHub)

---

📣 Credits

This fork uses Protocol Buffer definitions maintained by WPP Connect via wa-proto

Full credit is attributed to the original maintainers and contributors of Baileys:

· purpshell
· jlucaso1
· adiwajshing

<!-- Please do not replace my name with yours. It's disrespectful. -->

This fork includes additional enhancements and modifications by Lia Wynn

Special thanks to itsreimau for the fix to the updateBlockStatus implementation.

[!CAUTION]
⚠️ Modification, removal, or misrepresentation of these credits is strictly prohibited. Any redistribution or fork must preserve this section in its original form without exception.

```

---

## 📌 Cara Simpan

1. Buat file baru bernama `README.md` di root repo kamu.
2. Copy semua isi di atas (dari `# 🌱 @zavedyaid/baileys` sampai akhir).
3. Paste ke file `README.md`.
4. Save, commit, dan push.

```bash
git add README.md
git commit -m "docs: update README.md with improved formatting"
git push
```
