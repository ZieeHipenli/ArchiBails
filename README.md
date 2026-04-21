# Modified Whatsapp-API
<p align='center'>
  <img src="https://i.top4top.io/p_3763ouz4t0.jpeg" width="172">
</p>

--- 

## Usage
```json
"depencies": {
  "@whiskeysockets/baileys": "github:ZieeHipenli/ArchiBails"
}
```
## Import
```javascript
const {
  default:makeWASocket,
  // Other Options 
} = require('@whiskeysockets/baileys');
```

---
# How To Connect To Whatsapp
## With QR Code
```javascript
const {
  default: makeWASocket
} = require('@whiskeysockets/baileys');

const client = makeWASocket({
  browser: ['Ubuntu', 'Chrome', '20.00.1'],
  printQRInTerminal: true
})
```

## Connect With Number
```javascript
const {
  default: makeWASocket,
  fetchLatestWAWebVersion
} = require('@whiskeysockets/baileys');

const client = makeWASocket({
  browser: ['Ubuntu', 'Chrome', '20.00.1'],
  printQRInTerminal: false,
  version: fetchLatestWAWebVersion()
  // Other options
});

const number = "628XXXXX";
const code = await client.requestPairingCode(number.trim) /* Use : (number, "YYYYYYYY") for custom-pairing */

console.log("Ur pairing code : " + code)
```

# Sending messages

## send orderMessage
```javascript
const fs = require('fs');
const RinnImg = fs.readFileSync('./RinnImage');

await client.sendMessage(m.chat, {
  thumbnail: RinnImg,
  message: "Gotta get a grip",
  orderTitle: "7eppeli-Corporation",
  totalAmount1000: 72502,
  totalCurrencyCode: "IDR"
}, { quoted:m })
```

## send pollResultSnapshotMessage
```javascript
await client.sendMessage(m.chat, {
  pollResultMessage: {
    name: "ZieePenli-archimedes",
    options: [
      {
        optionName: "poll 1"
      },
      {
        optionName: "poll 2"
      }
    ],
    newsletter: {
      newsletterName: "ZieePenli | Information",
      newsletterJid: "1@newsletter"
    }
  }
})
```

## send productMessage
```javascript
await client.relayMessage(m.chat, {
  productMessage {
    title: "Hipenli.pdf",
    description: "zZZ...",
    thumbnail: { url: "./RinnImage" },
    productId: "EXAMPLE_TOKEN",
    retailerId: "EXAMPLE_RETAILER_ID",
    url: "https://t.me/xyziee",
    body: "Tido Sodap",
    footer: "Footer",
    buttons: [
      {
        name: "cta_url",
        buttonParamsJson: "{\"display_text\":\"ZieePenli-Hpl\",\"url\":\"https://t.me/xyziee\"}"
      }
    ],
    priceAmount1000: 72502,
    currencyCode: "IDR"
  }
})
```
Follow https://t.me/zieehpl kalau nak type message yg lain
