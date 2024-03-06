<h1 align="center">Welcomify</h1>
<h4 align="center">a cutting-edge canvas library for creating futuristic welcome cards.</h4>
<div align="center">
<p>
  <a href="https://github.com/oneofremii/Welcomify#readme" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg?style=flat-square" />
  </a>
  <a href="https://github.com/oneofremii/Welcomify/graphs/commit-activity" target="_blank">
    <img alt="Maintenance" src="https://img.shields.io/badge/Maintained%3F-yes-green.svg?style=flat-square" />
  </a>
  <a href="(https://github.com/oneofremii/Welcomify/blob/main/LICENSE" target="_blank">
    <img alt="License: GPL--3.0" src="https://img.shields.io/github/license/oneofremii/Welcomify?style=flat-square" />
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
    .setTitle("Welcome")
    .setName("Remii")
    .setAvatar(
      "https://raw.githubusercontent.com/Shiioriii/Welcomify/main/assets/avatar.png"
    )
    .setMessage("YOU ARE 300 MEMBERS!")
    .setBackground('https://raw.githubusercontent.com/Shiioriii/Welcomify/main/assets/background.jpg')
    .setColor("00FF38"); // without #

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
    .setTitle("Welcome")
    .setName(member.user.username)
    .setAvatar(member.user.displayAvatarURL({ format: 'png', dynamic: true }))
    .setMessage("YOU ARE 300 MEMBER!")
    .setBackground('https://raw.githubusercontent.com/oneofremii/Welcomify/main/assets/background.jpg')
    .setColor("00FF38"); // without #

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
### Output
<img src="/image/output.png" alt="Sample Welcome Message" width="400x" height="230px">

### Methods

<img src="/image/illustration.png" alt="Sample Welcome Message" width="400x" height="230px">


1.  **`.setTitle(title: string) (optional)`**
    - Sets the title of the welcome card.

2.  **`.setName(username: string) (optional)`**
    - Dynamically fetches the username into the welcome card.

3.  **`.setAvatar(avatarURL: string) (required)`**
    - Sets the display avatar in the welcome card.

4.  **`.setMessage(message: string) (optional)`**
    - Specifies a custom message into welcome card.

5.  **`.setBackground(backgroundURL: string) (optional)`**
    - Sets a custom background image for the welcome card.

6.  **`.setColor(colorCode: string) (optional)`**
    - Defines the color scheme of the `.setName`, use the format without the # symbol.



## Author

👤 **Remii**

- Website: https://fypmoon.org
- Twitter: [@shioriikwkmi](https://twitter.com/shioriikwkmi)
- Github: [@oneofremii](https://github.com/oneofremii)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/oneofremii/Welcomify/issues). You can also take a look at the [contributing guide](https://github.com/oneofremii/Welcomify/blob/master/CONTRIBUTING.md).

## Show your support

Give a ⭐️ if this project helped you!

<a href="https://www.patreon.com/oneofremii">
  <img src="https://c5.patreon.com/external/logo/become_a_patron_button@2x.png" width="160">
</a>

## 📝 License

Copyright © 2024 [Remii](https://github.com/oneofremii).<br />
This project is [GPL-3.0](https://github.com/oneofremii/Welcomify/blob/main/LICENSE) licensed.
