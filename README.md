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

- To fetch your own stats, simply type `!stats`
- Providing a list of users displays a table so their stats can be easily compared side by side.  You can fetch up to 6 users at a time:

```shell
!stats @jubi
