<p align="center">
  <a href="https://akaruidevelopment.github.io/Zeneth">
    <img width="200" src="https://cdn.discordapp.com/attachments/983797852008497164/1125422710072287252/Zeneth.png" alt="Zeneth">
  </a>
</p>

<h1 align="center">Zeneth</h1>

<div align="center">
  <b>A NodeJs Library that make interaction with discord api </b>
</div>

---

## Installation

```css
npm i zeneth
```
or
```css
yarn add zeneth
```

## Setup

```js
const {
    Client,
    Intents,
    GatewayEventNames,
} = require("zeneth");

const client = new Client({
    intents: Intents.Guilds | Intents.GuildMessages | Intents.MessageContent,
    token: "Token" ,
});


client.on(GatewayEventNames.Ready, () => {
    console.log("Ready!");
});

client.on(GatewayEventNames.MessageCreate, async(message) => {
    if (message.content === "!ping") {
        await client.createMessage(message.channelId, {
            content: `Pong!  ${client.ws.data.ping} ms`,
        });
    }
});
```

## Structure

```mermaid
graph LR;
A[Zeneth] --> B[Classes];
A --> C[Client];
A --> D[Error];
A --> E[Events];
A --> F[Plugins];
A --> G[Request];
A --> H[Typings];
A --> I[Utils];
A --> J[Websocket];
```

## LICENSE

[Apache 2.0](./LICENSE)

## Our ♥️ Contributors

<a href="https://github.com/Akaruidevelopment/zeneth/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=AkaruiDevelopment/zeneth"  alt="zeneth-contributors"/>
</a>
