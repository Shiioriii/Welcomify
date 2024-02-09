<h1 align="center">Welcomify</h1>
<h4 align="center">Transform greetings into art with Welcomify, a cutting-edge canvas library for crafting futuristic welcome cards.</h4>
<div align="center">
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-1.0.0-blue.svg?cacheSeconds=2592000?style=flat-square" />
  <a href="https://github.com/Shiioriii/Welcomify#readme" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg?style=flat-square" />
  </a>
  <a href="https://github.com/Shiioriii/Welcomify/graphs/commit-activity" target="_blank">
    <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg?style=flat-square" />
  </a>
  <a href="(https://github.com/Shiioriii/Welcomify/blob/main/LICENSE" target="_blank">
    <img alt="License: GPL--3.0" src="https://img.shields.io/github/license/Shiioriii/Welcomify?style=flat-square" />
  </a>
  <a href="https://twitter.com/shioriikwkmi" target="_blank">
    <img alt="Twitter: shioriikwkmi" src="https://img.shields.io/twitter/follow/shioriikwkmi.svg?style=social" />
  </a>
  <a href="https://npmjs.org/package/welcomify" target="_blank">
  <img alt="NPM Version" src="https://img.shields.io/npm/v/welcomify?style=flat-square&logo=npm" />
  </a>
  <a href="https://npmjs.org/package/welcomify" target="_blank">
  <img alt="NPM Downloads" src="https://img.shields.io/npm/dt/welcomify?style=flat-square&logo=npm">
  </a>
</p>
</div>

### 🏠 [Homepage](https://fypmoon.org/project/welcomify)

## Install

```sh
npm i welcomify
```

## Usage

#### This example code will create a welcome card and save it as a png.

```javascript
(async () => {
  // Importing modules
  const { Card } = require("welcomify");
  const fs = require("fs");

  // Card details here
  const card = new Card()
    .setName("Shiorii")
    .setAvatar(
      "https://raw.githubusercontent.com/Shiioriii/Welcomify/main/assets/avatar.png"
    )
    .setMessage("YOU ARE 300 MEMBERS!")
    .setBackground(
      "https://raw.githubusercontent.com/Shiioriii/Welcomify/main/assets/background.jpg"
    )
    .setColor("00FF38") // without #
    .setTitle("Welcome");

  // Building process
  const cardoutput = await card.build();

  // Save as image
  fs.writeFileSync("cardout.png", cardoutput);
  console.log("Done");
})();
```

#### Example For Discord.js Bot Used

```javascript
// Importing modules
const { Card } = require("welcomify");
const { AttachmentBuilder } = require("discord.js");

// Make sure to define client
client.on("guildMemberAdd", async (member) => {
  // Card details here
  const card = new Card()
    .setName("Shiorii")
    .setAvatar(
      "https://raw.githubusercontent.com/Shiioriii/Welcomify/main/assets/avatar.png"
    )
    .setMessage("YOU ARE 300 MEMBER!")
    .setBackground(
      "https://raw.githubusercontent.com/Shiioriii/Welcomify/main/assets/background.jpg"
    )
    .setColor("00FF38") // without #
    .setTitle("Welcome");

  // Building process
  const cardoutput = await card.build();

  // Fetch channel from members guild using ID
  const channel = member.guild.channels.cache.get("0000000000000000000");

  // Sends card to the "channel"
  await channel.send({
    files: [
      {
        attachment: cardoutput,
        name: `${member.id}.png`,
      },
    ],
  });
});
```

## Author

👤 **Shiorii**

- Website: https://fypmoon.org
- Twitter: [@shioriikwkmi](https://twitter.com/shioriikwkmi)
- Github: [@Shiioriii](https://github.com/Shiioriii)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/Shiioriii/Welcomify/issues). You can also take a look at the [contributing guide](https://github.com/Shiioriii/Welcomify/blob/master/CONTRIBUTING.md).

## Show your support

Give a ⭐️ if this project helped you!

<a href="https://www.patreon.com/shiorii">
  <img src="https://c5.patreon.com/external/logo/become_a_patron_button@2x.png" width="160">
</a>

## 📝 License

Copyright © 2024 [Shiorii](https://github.com/Shiioriii).<br />
This project is [GPL-3.0](https://github.com/Shiioriii/Welcomify/blob/main/LICENSE) licensed.
