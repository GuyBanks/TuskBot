# TuskBot

**`TuskBot` is a Rocket League Discord Bot focused on tracking player ranks and in-game stats.**

## Getting Started

### [Install TuskBot](https://discordapp.com/oauth2/authorize?&client_id=708694380869058600&permissions=268848192&scope=bot) on your discord server

#### "Manage Roles" permission

- The "Manage Roles" permission is optional.  If granted, `TuskBot` will create 19 roles, one for every Rocket League rank (unless they already exist).  These will be named:
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
  - Then: everytime a user is registered or their rank is checked, they will be automatically assigned the role of their highest rank.

#### Type `!help`

- Once the bot is installed, you can type `!help` to see a list of all possible commands.

### Register your Rocket League account

- Most commands won't work unless you have registered your Rocket League account first:

```shell
!register <account-id> [platform]
```

- **Steam**:
  - **`<account-id>`**: The unique ID identifying your steam account.  You can use either:
    - The number at the end of a link like `http://steamcommunity.com/profiles/76561198257073170`.  In this case it would be `76561198257073170`.
    - The text at the end of a link like `https://steamcommunity.com/id/jubishop`.  In this case it would be `jubishop`.
    - On the desktop version of Steam, you can find this link by right-clicking anywhere in the empty space of your profile and selecting `Copy Page Url`.  Then simply paste it into the address bar of your browser.
  - **`[platform]`**:  This defaults to steam, so you can omit it.
  - ***Example***: In this case, the user could register with: `!register 76561198257073170` or: `!register jubishop`.

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

![Image of Ranks](https://raw.githubusercontent.com/jubishop/TuskBot/master/images/ranks.png)

- To get your own ranks, simply type `!ranks`
- To get the ranks of another registered user, follow the command with the name, nickname, or @ of another member.
  - ***Example***: `!ranks jubishop`
  - ***Example***: `!ranks @jubishop`
- If the `Manage Roles` permission has been granted, every time a rank is checked, the role of that user will be updated to their current highest rank.

## Stats

There are 3 commands for getting stats in various ways.

### Lifetime Stats

You can fetch lifetime stats, across all game-modes and playlists, with:

```shell
!stats [user1] [user2] [user3] ...
```

![Image of Stats](https://raw.githubusercontent.com/jubishop/TuskBot/master/images/stats.png)

- You can click the :arrow_left: and :arrow_right: buttons to flip between the different pages of statistics.
- To fetch your own stats, simply type `!stats`
- If you provide a list of users it will display a table so their stats can be easily compared side by side.  You can fetch up to 6 users at a time.  The photo above was generated with the command:

```shell
!stats @jubi @Zoynx @Jetpoof @Piaka @Tombst0ne @FezDispenser
```

### Series Stats

Lifetime stats aren't great for comparing players.  Someone who mostly plays Duel 1v1 is going to have wildly different stats than someone that prefers Standard 3v3.  The `!series` command provides a way to view stats for the specific games where all the players were playing together.  This makes for much more interesting comparisons.

```shell
!series [user1] [user2] [user3] ...
```

![Image of Series](https://raw.githubusercontent.com/jubishop/TuskBot/master/images/series.png)

- The image above comes from running the command `!series @jubi @FezDispenser` after `@jubi` and `@FezDispenser` played a series of 2v2 games together.
- This data is gathered from [ballchasing.com](http://ballchasing.com).  Stats are generated from the uploaded replays of the user who executes the `!series` command.  Your replays must be marked `public` for TuskBot to access them.  The easiest way to have all your replay files automatically uploaded is using [BakkesMod](https://bakkesmod.com/).  You can find instructions [here](https://ballchasing.com/doc/faq#upload).
- Because of API rate limits, `!series` will only work off the games you've played in the last 36 hours.  The best way to use this feature is to run it sometime within the following day after a session of playing together.
