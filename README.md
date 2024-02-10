# ZMK Firmware: Personal fork

This is a legacy version of my personal ZMK fork containing various experimental features used in
my [zmk-config](https://github.com/urob/zmk-config/). This particular branch is **no longer maintained**.
For a current branch, see the [main branch](https://github.com/urob/zmk/tree/main) of this repo.

Note that this legacy branch adds mouse support using the [original mouse
PR)(https://github.com/zmkfirmware/zmk/pull/778) by krikun, using a slightly different api
then the official mouse api in ZMK.

Below is a list of features currently included in the `main` branch _on top of_
the official ZMK master branch.

- **mouse** (PR [#778](https://github.com/zmkfirmware/zmk/pull/778)) - official PR + ftc's update + [update to Zephyr 3.2](https://github.com/urob/zmk/tree/mouse-3.2) + some safeguards + enforce hog device fix
- **swapper** (PR [#1366](https://github.com/zmkfirmware/zmk/pull/1366)) - official PR + fixes needed for Zephyr 3.2
- **smart-word** (PR [#1451](https://github.com/zmkfirmware/zmk/pull/1451)) - official PR, updated to Zephyr-3.2
- **fix-key-repeat** - fix [key-repeat rolling issue](https://github.com/zmkfirmware/zmk/issues/1207)
- **on-release-for-tap-preferred** - [on-release option for tap-preferred](https://github.com/celejewski/zmk/commit/d7a8482712d87963e59b74238667346221199293) by Andrzej
- **adv360pro** (PR [#1454](https://github.com/zmkfirmware/zmk/pull/1454)) - offical PR
- **zen-tweaks** - [display & battery improvements](https://github.com/caksoylar/zmk/tree/caksoylar/zen-v1%2Bv2) by Cem Aksoylar

In order to use this branch with Github Actions, replace the contents of `west.yml` in
your `zmk-config/config` directory with the following contents:

```
manifest:
  remotes:
    - name: urob
      url-base: https://github.com/urob
  projects:
    - name: zmk
      remote: urob
      revision: main
      import: app/west.yml
  self:
    path: config
```
