# TJSON

A lightweight, more forgiving alternative to JSON for Haxe projects — especially great for mods, config files, or anything alike.

This is a fork of the original [TJSON](https://github.com/JWambaugh/TJSON) parser, updated and cleaned up for use in **Lime/OpenFL/FNF-style projects**. It's designed to be more resilient and user-friendly than standard `haxe.Json`.

---

## 🌟 Features

- ✅ Comments! Supports `//` and `/* block comments */`
- ✅ Keys **don’t need quotes**
- ✅ Strings can use **single or double quotes**
- ✅ Commas are **optional**
- ✅ Trailing commas **won’t crash** your file
- ✅ Helpful error messages with line numbers

---

## 💾 Installation

Install via haxelib by running the following in your command line:

`haxelib git tjson https://github.com/moxie-coder/TJSON/`

Depending on your setup, if you're updating for legacy projects, be sure to add the following to your .hxml file:

`-lib tjson`

Otherwise, include this in your Project.xml as such

`<haxelib name="tjson"/>`

Make sure it does *not* have `version="1.4.0"` in it. Simple as that!

HXP Installation:

¯\_(ツ)_/¯

---

## 🚀 Usage

<!-- Insert links here -->
For Non-FNF people looking at this, check out the [old Usage page](./docs/USAGE.md).

```haxe
import tjson.TJSON;

var raw:String = Assets.getText("assets/data/character.tjson");
var data:Dynamic = TJSON.parse(raw);
trace(data.name); // e.g. "Boyfriend"
```

## 📜 License

This project is based on the original TJSON parser by Jordan CM Wambaugh, licensed under the BSD 2-Clause License.  
See [LICENSE](./LICENSE) for details.

Modifications and modernizations by Moxie, 2025.

