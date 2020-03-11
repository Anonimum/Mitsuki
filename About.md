# Discord Welcome Image. 

Yaaww Selamat Pagi/Siang/Sore/Malam Buat Kalian Hwhw... Yups! Nih Buat Kalian Yang Pengen Welcome Image... Bisa Langsung Disimak Yaaww!
Jadi... Welcome Image Yang Aku Buat Ini... Ga Sebagus Kayak Punya Orang - Orang, Jadi Cukup - Cukup-in Lah Yaaaa Wkwkw... Kalau Mau Kalian
Ubah Silahkan, Biar Bot Kalian Jadi Semakin Bagus. Selamat Mencoba!

## About

### Made by Meliodas.#4613 With Luve :3
* Enable/Disable Welcome Image Sesuka Kalian
* Channel Bisa Di Set Dimanapun Kalian Mau
* Message Bisa Di Custom... Max 34 Huruf (Recomended) Atau Lebih (Ubah Sendiri)
* Background Bisa Kalian Set Sendiri Menggunakan Link (`.JPG` / `.PNG`)

## Installation

* Install Quick.db `npm i quick.db`
* Install Node-Superfetch `npm i node-superfetch`
* Install Canvas `npm i canvas`
* Install Canvas-Constructor `npm i canvas-constructor`

## Read And Learn

### Basic Code

* Berikut Ini Adalah Basic Code, Ubah Sendiri Jika Ada Yang Ingin Di Ubah.
* Pastikan Ke-4 Package Yang Ada Diatas Sudah Kalian Install!

```js
const Discord = require("discord.js");
const db = require("quick.db");

const Token = "TOKEN!"
cons Prefix = "PREFIX!"

const bot = new Discord.Client();

bot.on("ready", async() => {
  console.log("Welcome Image Ready!")
});

bot.on("message", async(msg) => {
  const args = msg.content.split(" ");
  let command = msg.content.toLowerCase().split(" ")[0];
  command = command.slice(Prefix.length);
});

bot.login(Token);
```

### Enable & Disable

* **Enable**: Meng-Aktifkan Welcome Image
* **Disable**: Meng-Nonaktifkan Welcome Image

```js
bot.on("message", async(msg) => {
  const args = msg.content.split(" ");
  let command = msg.content.toLowerCase().split(" ")[0];
  command = command.slice(Prefix.length);
  const Argumen = args[1];
  
  if (command.toUpperCase() === "WELCOME") {
    if (Argumen.toUpperCase() === "ENABLE") {
      msg.channel.send(`Enable`);
      db.set(`${msg.guild.id}.Config.Welcome.ED`, "YA");
    };

    if (Argumen.toUpperCase() === "DISABLE") {
      msg.channel.send(`Disable`);
      db.set(`${msg.guild.id}.Config.Welcome.ED`, "TIDAK");
    };
  };
});
```

<img src="https://cdn.discordapp.com/attachments/684577548381978657/687164334727888920/unknown.png"/>

### Channel
```js
bot.on("message", async msg => {
  const args = msg.content.split(" ");
  let command = msg.content.toLowerCase().split(" ")[0];
  command = command.slice(Prefix.length);
  const Argumen = args[1];

  if (command.toUpperCase() === "WELCOME") {
    if (Argumen.toUpperCase() === "CHANNEL") {
      let Channel = msg.mentions.channels.first();
      if (!Channel) {
        msg.channel.send(`Channel??`);
      } else {
        msg.channel.send(`Channel: ${Channel.id}`);
        db.set(`${msg.guild.id}.Config.Welcome.Channel`, Channel.id);
      };
    };
  };
});
```

<img src="https://cdn.discordapp.com/attachments/684577548381978657/687165092458135582/unknown.png"/>

### Message
```js
bot.on("message", async msg => {
  const args = msg.content.split(" ");
  let command = msg.content.toLowerCase().split(" ")[0];
  command = command.slice(Prefix.length);
  const Argumen = args[1];

  if (command.toUpperCase() === "WELCOME") {
    if (Argumen.toUpperCase() === "MESSAGE" || Argumen.toUpperCase() === "MSG") {
      let Message = args.slice(2).join(" ");
      if (Message.length > 34) {
        msg.channel.send(`Message??`);
      } else {
        msg.channel.send(`Message: ${Message}`);
        db.set(`${msg.guild.id}.Config.Welcome.Message`, Message);
      };
    };
  };
});
```

<img src="https://cdn.discordapp.com/attachments/684577548381978657/687165271529750534/unknown.png"/>

### Background
```js
bot.on("message", async msg => {
  const args = msg.content.split(" ");
  let command = msg.content.toLowerCase().split(" ")[0];
  command = command.slice(Prefix.length);
  const Argumen = args[1];

  if (command.toUpperCase() === "WELCOME") {
    if (Argumen.toUpperCase() === "BACKGROUND" || Argumen.toUpperCase() === "BG") {
      let Background = args.slice(2).join(" ");
      if (!Background) {
        msg.channel.send(`Background??`);
      } else {
        msg.channel.send(`Background: ${Background}`);
        db.set(`${msg.guild.id}.Config.Welcome.Background`, Background);
      };
    };
  };
});
```

<img src="https://cdn.discordapp.com/attachments/684577548381978657/687165986943926273/unknown.png"/>

## Results

<img src="https://cdn.discordapp.com/attachments/684577548381978657/687166866149736448/unknown.png"/>




