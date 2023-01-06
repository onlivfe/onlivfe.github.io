# General design considerations

## Features / "Selling points"

- Single identity/profile across multiple social (VR) platforms
- See people currently online
  - ~~Single area with multiple platforms~~
- Reduce the friction of changing platorms due to networking effect & lock-in
  - Sharing of platform account details
  - Options to easily send & accept friend requests of mapped accounts

## Data

- UI's data structure does not need to reflect API structures
  - API breaking changes shouldn't need UI code changes
- All possibly cacheable data should be cached
  - UI needs to request updates to data when showing it, as it's possibly from an old cached version
- Data could be stored with timestamps for possible statistical analysis

## Hurdles

- managing multiple user profiles/identities, with multiple accounts
- multiple accounts for a single user
  - SOLUTION: create "mappings", which can be shared, and are not tied to a unique id globally
  - if there is a sync/someone updates a mapping from someone else
    - check existing user ids when there is a profile sync push
    - ask the user if they want to overwrite
- using an account on multiple computers/vms

## UI design

- Displays which instances your friends are in, sorted by most friends in instance (usecase: "I want to have a good time with my friends, where should I join for that?")
- Display who is online (usecase: "I like X and Y, are either of them online?")
- Display visuals (preference to icons and colors), rather than text, if and as long as it makes sense
  - world icons and user icons
  - in VRCX, it does not display world icons
- Expandable tabs, or draggable windows/layers (optional)
  - General idea of viewing information at a glance and allow it to be compared (if possible)
- Responsibe design
  - breakpoint for wider screens: wide would be sidebar, narrow would be modal/draggable window (also selectable by user for override)
