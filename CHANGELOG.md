<!--
SPDX-FileCopyrightText: 2023-2024 Mirian Margiani
SPDX-License-Identifier: GFDL-1.3-or-later
-->

# Changelog

## 2.1.0 (2024-06-22)

- added `ComboData.reset(data)` to easily reset the current index to the first
  menu item matching `data`
- `ComboData` now binds itself to the parent's `cdata` property, if such a
  property is defined
- added complete examples to the documentation

## 2.0.0 (2023-06-29)

- moved the ready-made Attribution component from
  `Opal/<module>/Opal<module>Attribution.qml` to `Opal/Attributions/Opal<module>Attribution.qml`
- you no longer have to import all Opal modules on the “About” page to attribute them,
  simply use `import "../modules/Opal/Attributions"` to access all attributions

## 1.0.0 (2023-06-23)

- first fully-featured and stable release
