<h1 align="center">Telegram Bot</h1>

<div align="center">

Node.js module to interact with the official [Telegram Bot API](https://core.telegram.org/bots/api).


[![Bot API](https://img.shields.io/badge/Bot%20API-v.5.2-00aced.svg?style=flat-square&logo=telegram)](https://core.telegram.org/bots/api)
[![npm package](https://img.shields.io/npm/v/@guru-node/telegram-bot?logo=npm&style=flat-square)](https://www.npmjs.org/package/@guru-node/telegram-bot)
[![Build Status](https://img.shields.io/travis/guru-node/guru-node/telegram-bot/master?style=flat-square&logo=travis)](https://travis-ci.org/guru-node/guru-node/telegram-bot)
[![Coverage Status](https://img.shields.io/codecov/c/github/guru-node/guru-node/telegram-bot?style=flat-square&logo=codecov)](https://codecov.io/gh/guru-node/guru-node/telegram-bot)

[![https://telegram.me/node_telegram_bot_api](https://img.shields.io/badge/💬%20Telegram-Channel-blue.svg?style=flat-square)](https://telegram.me/node_telegram_bot_api)
[![https://telegram.me/ntbasupport](https://img.shields.io/badge/💬%20Telegram-Group-blue.svg?style=flat-square)](https://telegram.me/ntbasupport)
[![https://telegram.me/Yago_Perez](https://img.shields.io/badge/💬%20Telegram-Yago_Perez-blue.svg?style=flat-square)](https://telegram.me/Yago_Perez)

</div>

## Install

```sh
npm i @guru-node/telegram-bot
```

## Usage

```js
const TelegramBot = require('@guru-node/telegram-bot');

// replace the value below with the Telegram token you receive from @BotFather
const token = 'YOUR_TELEGRAM_BOT_TOKEN';

// Create a bot that uses 'polling' to fetch new updates
const bot = new TelegramBot(token, {polling: true});

// Matches "/echo [whatever]"
bot.onText(/\/echo (.+)/, (msg, match) => {
  // 'msg' is the received Message from Telegram
  // 'match' is the result of executing the regexp above on the text content
  // of the message

  const chatId = msg.chat.id;
  const resp = match[1]; // the captured "whatever"

  // send back the matched "whatever" to the chat
  bot.sendMessage(chatId, resp);
});

// Listen for any kind of message. There are different kinds of
// messages.
bot.on('message', (msg) => {
  const chatId = msg.chat.id;

  // send a message to the chat acknowledging receipt of their message
  bot.sendMessage(chatId, 'Received your message');
});
```

## Documentation

* [Usage][usage]
* [Examples][examples]
* [Tutorials][tutorials]
* [Help Information][help]
* API Reference [api-release] / [development][api-dev] / [experimental][api-experimental])
* [Contributing to the Project][contributing]
* [Experimental Features][experimental]

_**Note**: Development is done against the **master** branch.
Code for the latest release resides on the **release** branch.
Experimental features reside on the **experimental** branch._


## Community

We thank all the developers in the Open-Source community who continuously
take their time and effort in advancing this project.
See our [list of contributors][contributors].

We have a [Telegram channel][tg-channel] where we post updates on
the Project. Head over and subscribe!

We also have a [Telegram  group][tg-group] to discuss issues related to this library.

Some things built using this library that might interest you:

* [tgfancy](https://github.com/GochoMugo/tgfancy): A fancy, higher-level wrapper for Telegram Bot API
* [@guru-node/telegram-bot-middleware](https://github.com/idchlife/@guru-node/telegram-bot-middleware): Middleware for @guru-node/telegram-bot
* [teleirc](https://github.com/FruitieX/teleirc): A simple Telegram ↔ IRC gateway
* [bot-brother](https://github.com/SerjoPepper/bot-brother): Node.js library to help you easily create telegram bots
* [redbot](https://github.com/guidone/node-red-contrib-chatbot): A Node-RED plugin to create telegram bots visually
* [node-telegram-keyboard-wrapper](https://github.com/alexandercerutti/node-telegram-keyboard-wrapper): A wrapper to improve keyboards structures creation through a more easy-to-see way (supports Inline Keyboards, Reply Keyboard, Remove Keyboard and Force Reply)

## License

**The MIT License (MIT)**

Copyright © 2019 Yago

[usage]:https://github.com/guru-node/guru-node/telegram-bot/tree/master/doc/usage.md
[examples]:https://github.com/guru-node/guru-node/telegram-bot/tree/master/examples
[help]:https://github.com/guru-node/guru-node/telegram-bot/tree/master/doc/help.md
[tutorials]:https://github.com/guru-node/guru-node/telegram-bot/tree/master/doc/tutorials.md
[api-dev]:https://github.com/guru-node/guru-node/telegram-bot/tree/master/doc/api.md
[api-release]:https://github.com/guru-node/guru-node/telegram-bot/tree/release/doc/api.md
[api-experimental]:https://github.com/guru-node/guru-node/telegram-bot/tree/experimental/doc/api.md
[contributing]:https://github.com/guru-node/guru-node/telegram-bot/tree/master/CONTRIBUTING.md
[contributors]:https://github.com/guru-node/guru-node/telegram-bot/graphs/contributors
[experimental]:https://github.com/guru-node/guru-node/telegram-bot/tree/master/doc/experimental.md
[tg-channel]:https://telegram.me/node_telegram_bot_api
[tg-group]:https://telegram.me/ntbasupport
