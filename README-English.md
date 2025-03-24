# PermBook

**PermBook** is a plugin that helps you manage and distribute `LuckPerms` permission nodes through book items in Minecraft.

## Key Features

- **Requires the LuckPerms plugin.**
- Create and distribute books containing permission nodes using commands:
  - Permanent: `/permbook create <permission-node> <world>`
  - Temporary: `/permbook create-temp <permission-node> <duration> <world>` (e.g., 1d, 3h, 30m)
- Right-clicking the book opens a GUI where players can choose whether to apply the permission.
- Permissions are not duplicated if the player already has them.
- Fully customizable GUI layout, button design, and messages.
- Permission grants are logged to allow history tracking.
- Supports tab completion for easier command usage.

## Commands

| Command                                                      | Description                                                                                  |
| ------------------------------------------------------------ | -------------------------------------------------------------------------------------------- |
| `/permbook create <permission-node> <world>`                 | Creates a book with a permission node for the specified world (permanent).                   |
| `/permbook create-temp <permission-node> <duration> <world>` | Creates a book with a permission node that lasts for a specific duration in the given world. |
| `/permbook reload`                                           | Reloads configuration files (`permbook.yml`, `messages.yml`).                                |

## Configuration Files

### ``: Permission Book Item Settings

```yaml
permbook:
  name: "&ePermission Book"
  lore:
    - ""
    - "&7Right-click this book to obtain the permission."
    - ""
    - "&7Permission: &e{perm}"
    - "&7World: &e{world}"
    - ""

temp_permbook:
  name: "&eTemporary Permission Book"
  lore:
    - ""
    - "&7Right-click this book to obtain the permission."
    - ""
    - "&7Permission: &e{perm}"
    - "&7Duration: &e{duration}"
    - "&7World: &e{world}"
    - ""
```

- Use placeholders like `{perm}`, `{duration}`, and `{world}` to display relevant info.
- Even beginners can easily customize the item appearance.

### ``: Messages and GUI Settings

```yaml
messages:
  no-console: "&cThis command can only be used by players."
  usage-use: "&eUsage:\n&f/permbook reload\n&f/permbook create <LuckPerms Permission> <World>\n&f/permbook create-temp <LuckPerms Permission> <Duration> <World>"
  usage-create: "&cUsage: /permbook create <LuckPerms Permission> <World>"
  usage-temp-create: "&cUsage: /permbook create-temp <Permission Node> <Duration> <World> (e.g., 1d, 2h, 30m)"
  book-created: "&aBook with LuckPerms permission '{perm}' has been created. (Applies to {world})"
  temp-book-created: "&aBook with LuckPerms permission '{perm}' has been created for {duration}. (Applies to {world})"
  already-has-perm: "&cYou already have this permission!"
  perm-registered: "&aLuckPerms permission '{perm}' has been granted!"
  perm-registered-temp: "&aLuckPerms permission '{perm}' has been granted for {duration}! (Applies to {world})"
  perm-cancelled: "&cPermission grant has been cancelled."
  perm-fail: "&cAn error occurred while applying the permission. Check the console."
  duration-parse-fail: "&cCould not parse the duration. Permission was applied permanently."
  reload-complete: "&aPermBook configuration reloaded!"
  no-permission: "&cYou do not have permission to use this command."

gui:
  title: "Do you really want to apply this permission?"

  cancel-name: "&cCancel"
  cancel-lore:
    - ""
    - "&7Click to cancel permission grant."
    - ""

  confirm-name: "&aConfirm"
  confirm-lore:
    - ""
    - "&7Click to apply the permission."
    - ""
    - "&7Double-check before proceeding."
    - "&7Permission: &e{perm}"
    - "&7Duration: &e{duration}"
    - "&7World: &e{world}"
    - ""

  info-name: "&eAre you sure you want to apply this permission?"
  info-lore:
    - ""
    - "&7Double-check before proceeding."
    - "&7Permission: &e{perm}"
    - "&7Duration: &e{duration}"
    - "&7World: &e{world}"
    - ""
    - "&7Left: Cancel"
    - "&7Right: Confirm"
    - ""

  cancel-slots: "0-3"
  confirm-slots: "5-8"
```

- Customize button names, descriptions, and layout freely.
- All placeholders `{perm}`, `{duration}`, `{world}` can be used inside GUI text.

### ``: Permission Grant Logs

```yaml
logs:
- playerName, [2025-03-24 18:33], test.perm, ALL
- playerName, [2025-03-24 18:33], test.perm2, 1d, world
```

- Every successful permission grant is logged with: `- playerName, [datetime], permission node, duration, world`
- Makes it easy to audit and track permission usage.

## Installation & Usage

1. Install the `LuckPerms` plugin first.
2. Place the `PermBook` plugin JAR into your server's plugins folder.
3. Start the server to generate `permbook.yml`, `messages.yml`, and `data.yml`.
4. Use commands to generate permission books and give them to players.
5. Players right-click the books to open a GUI and choose whether to apply the permission.

---

## Dependency

- **LuckPerms (required)**

---

## Developer

- Angie\_OvO

---

If you encounter any issues or have feature requests, feel free to reach out via Discord: **01\_jeong\_ho**

