# TuskBot

**`TuskBot` is a Rocket League Discord Bot focused on tracking player ranks and in-game stats.**

![Image of Tusk](./images/tusk.png)

## Getting Started

### [Install TuskBot](https://discordapp.com/oauth2/authorize?&client_id=708694380869058600&permissions=268848192&scope=bot) on your discord server

#### "Manage Roles" permission

- If the "Manage Roles" permission is granted, `TuskBot` will create 19 new roles (unless they already exist).  These will be named:
  - `Bronze I`
  - `Bronze II`
  - `Bronze II`
  - `Silver I`
  - `Silver II`
  - `Silver III`
  - `Gold I`
  - `Gold II`
  - `Gold III`
  - `Platinum I`
  - `Platinum II`
  - `Platinum III`
  - `Diamond I`
  - `Diamond II`
  - `Diamond III`
  - `Champion I`
  - `Champion II`
  - `Champion III`
  - `Grand Champ`
  - Then: everytime a `!register` or `!ranks` is executed, that player will be automatically assigned the role of their highest rank.
  - You can choose to add this permission at any time after install and `TuskBot` will still go to work adding these roles and assigning them to players upen execution of `!register` or `!ranks`

#### Type `!help`

- Once the bot is installed, you can type `!help` to see a list of all possible commands.

### Register your Rocket League account

- Most commands won't work unless you have registered your Rocket League account first:

```shell
!register <account-id> [platform]
```

- **Steam**:
  - **`<account-id>`**: This is the unique ID that identifies your steam account.  You can use either:
    - The number at the end of a link like `http://steamcommunity.com/profiles/76561198257073170`.  In this case it would be `76561198257073170`.
    - The text at the end of a link like `https://steamcommunity.com/id/jubishop`.  In this case it would be `jubishop`.
    - On the desktop version of Steam, you can find this link by right-clicking anywhere in the empty space of your profile and selecting `Copy Page Url`.  Then simply paste it into the address bar of your browser.
  - **`[platform]`**:  This defaults to steam, so you can omit it.
  - ***Example***: In this case, the player could register with: `!register 76561198257073170` or: `!register jubishop`.

- **Playstation**:
  - **`<account-id>`**:  This is your PSN.
  - **`[platform]`**: This should be `ps`.
  - ***Example***: If your PSN is `jubishop`, you'd register with: `!register jubishop ps`

- **XBox**:
  - **`<account-id>`**:  This is your Gamertag.
  - **`[platform]`**: This should be `xbox`.
  - ***Example***: If your Gamertag is `jubishop`, you'd register with: `!register jubishop xbox`

- **Switch**:  Sorry, Switch is not yet supported.

## Ranks

```shell
!ranks [member]
```

![Image of Ranks](./images/ranks.png)

- To get your own ranks, simply type `!ranks`
- To get the ranks of another registered player, follow the command with the name, nickname, or @ of another discord member.
  - ***Example***: `!ranks jubi`
  - ***Example***: `!ranks @jubi`
- If the `Manage Roles` permission has been granted, every time a rank is checked, the role of that player will be updated to their current highest rank.

## Stats

There are 3 commands for getting stats in various ways.

### Lifetime Stats

You can fetch lifetime stats, across all game-modes and playlists, with:

```shell
!stats [member1] [member2] [member3] ...
```

![Image of Stats](./images/stats.png)

- You can click the :arrow_left: and :arrow_right: buttons to flip between the different pages of statistics.
- To fetch your own stats, simply type `!stats`
- If you provide a list of players it will display a table so their stats can be easily compared side by side.  You can fetch up to 6 players at a time.
- The image above was generated with the command:

```shell
!stats @jubi @Zoynx @Jetpoof @Piaka @Tombst0ne @FezDispenser
```

### Series Stats

Lifetime stats aren't great for comparing players.  Someone who mostly plays Duel 1v1 is going to have wildly different stats than someone that prefers Standard 3v3.  The `!series` command provides a way to view stats for the specific games where all the players were playing together.  This makes for much more interesting comparisons.

```shell
!series [member1] [member2] [member3] ...
```

![Image of Series](./images/series.png)

- You can click the :arrow_left: and :arrow_right: buttons to flip between the different pages of statistics.
- To fetch your own stats, simply type `!series`
- This data is gathered from [ballchasing.com](http://ballchasing.com).  Stats are generated from the uploaded replays of the player who executes the `!series` command.  Your replays must be marked `public` for TuskBot to access them.  The easiest way to have all your replay files automatically uploaded is using [BakkesMod](https://bakkesmod.com/).  You can find instructions [here](https://ballchasing.com/doc/faq#upload).
- **If you do not upload your replays to [ballchasing.com](http://ballchasing.com), you will get 0 results from `!series`.**
- Because of API rate limits, `!series` will only work off the games you've played in the last 36 hours.
- If you provide a list of players it will display a table so their stats can be easily compared side by side.  You can fetch up to 6 players at a time.
- After a session of playing Doubles together, the image above was generated with the command:

```shell
!series @jubi @FezDispenser
```

### Alltime Series Stats

Everytime a `!series` command is executed, `TuskBot` stores those replays in its own database.  The `!alltime` command uses those stored replays to show you the aggregate data of all the `!series` commands you've ever run.  So as long as you execute a `!series` command at least once every 36 hours, you'll be able to use `!alltime` to get the complete comparative stats of your games ever since you began using `TuskBot`.

```shell
!alltime [member1] [member2] [member3] ...
```

- The display format for `!alltime` is exactly the same as `!series`.
- The `!alltime` command will only pull data from the stored replays inside its local database.  Only the `!series` command will get new data from [ballchasing.com](http://ballchasing.com)
- **If you do not upload your replays to [ballchasing.com](http://ballchasing.com), or you never run the `!series` command, you will get 0 results from `!alltime`.**

### URL Commands

Use the `!help` command to learn about simple commands to get URLs to specific player pages on [ballchasing.com](http://ballchasing.com), [calculated.gg](http://calculated.gg), [rocketleague.tracker.network](http://rocketleague.tracker.network), etc.

## Try it out before installing

You're welcome to [join the server](https://discord.gg/7xqkAVd) where `TuskBot` was developed and always resides in order to try it out for yourself.

## Bugs / Feedback

Feel free to provide feedback of any sort through [Issues](https://github.com/jubishop/TuskBot/issues) here on this github repo.
