<!--
SPDX-FileCopyrightText: 2023 Mirian Margiani
SPDX-License-Identifier: GFDL-1.3-or-later
-->

# Data combo box for Sailfish apps

This module provides an extension for combo boxes to access the current value
instead of the label.

Sailfish Silica's `ComboBox` combo boxes expose three values: current index,
current item, and value. The `value` property actually holds the current
item's `text` value.

An item's label and actual value are often not the same, though. This extension
allows to define a custom property that is exposed as `currentData`.

The helper function `indexOfData` determines the index of a given data
value. This can then be used to change the combo box's current index.

## Usage

Define the combo box like any other `ComboBox`, then add a `ComboData` child.

If you want to use `currentData`, create a `currentData` property in the parent
`ComboBox`. It's value will automatically be updated by `ComboData`.

For convenience, `ComboData.indexOfData` will be bound automatically to the
`indexOfData` property of `ComboData`'s parent - if such a property exists.

All `MenuItem` instances must have a property with the name defined in
`ComboData.dataRole`.

```{qml}
import QtQuick 2.0
import Sailfish.Silica 1.0
import Opal.ComboData 1.0

ComboBox {
    label: qsTr("Fruit")

    property string currentData  // expose ComboData.currentData - remove if not needed
    property var indexOfData  // expose ComboData.indexOfData - remove if not needed
    ComboData { dataRole: "value" }

    menu: ContextMenu {
        MenuItem {
            property string value: "fruit-1"
            text: qsTr("Banana")
        }
        MenuItem {
            property string value: "fruit-2"
            text: qsTr("Kiwi")
        }
        MenuItem {
            property string value: "fruit-3"
            text: qsTr("Pear")
        }
    }
}
```

## Screenshots

This is a non-visual module, so there are no screenshots.

## How to use

You do not need to clone this repository if you only intend to use the module in
another project. Simply download the
[latest release bundle](https://github.com/Pretty-SFOS/opal-combodata/releases/latest).

### Setup

Follow the main documentation for installing Opal modules
[here](https://github.com/Pretty-SFOS/opal/blob/main/README.md#using-opal).

### Configuration

See [`doc/gallery.qml`](doc/gallery.qml) for an example. Copy the file to get
started.

### Documentation

Extensive documentation is included in the release bundle and can be added to
QtCreator via Extras → Settings → Help → Documentation → Add.

## Translations

To **use** packaged translations in your project, follow the main documentation for
using Opal modules [here](https://github.com/Pretty-SFOS/opal#using-opal).

You can also **contribute** translations. If an app uses Opal modules, consider
updating its translations at the source (i.e. here), so that all Opal users can
benefit from it. Translations are managed using
[Weblate](https://hosted.weblate.org/projects/opal).

Please prefer Weblate over pull requests (which are still welcome, of course).
If you just found a minor problem, you can also
[leave a comment in the forum](https://forum.sailfishos.org/t/opal-qml-components-for-app-development/15801)
or [open an issue](https://github.com/Pretty-SFOS/opal/issues/new).

Please include the following details:

1. the language you were using
2. where you found the error
3. the incorrect text
4. the correct translation

See [the Qt documentation](https://doc.qt.io/qt-5/qml-qtqml-date.html#details) for
details on how to translate date formats to your local format.

## License

    Copyright (C) 2023  Mirian Margiani
    Program: opal-combodata

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
