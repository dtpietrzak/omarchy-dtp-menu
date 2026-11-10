# omarchy-dtp-menu

The Omarchy menu (Super+Space and the bar button) restyled to match the workspace control menus.

- The card opens in the corner beside the menu button and uses the bar's background, with no dim behind it.
- The highlighted row has the hover fill and a 1px accent outline. Its text keeps the normal color.
- The card background follows the bar (opaque, glassy or clear), with blur behind it when the bar is glassy.
- Icons are 1.5x the body text size. Labels are body size and the search line is title size.

Menu behavior is Omarchy's own code. Only the look and placement changed (see `diff upstream/Menu.qml Menu.qml`). The manifest marks this as a clone of `omarchy.menu`, so it replaces the stock menu while enabled, and `omarchy plugin remove io.github.dtpietrzak.menu` brings the stock one back.

```bash
omarchy plugin add https://github.com/dtpietrzak/omarchy-dtp-menu.git --enable
```

## Taking in a newer Omarchy menu

`upstream/` holds the untouched Omarchy files this was built from. Merge a newer stock `Menu.qml` with:

```bash
git merge-file Menu.qml upstream/Menu.qml /usr/share/omarchy/shell/plugins/menu/Menu.qml
cp /usr/share/omarchy/shell/plugins/menu/Menu.qml upstream/Menu.qml
```

Resolve any conflict markers, then do the same for `MenuModel.js` and `BarWidget.qml`.
