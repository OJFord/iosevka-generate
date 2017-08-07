# Iosevka Generate

Iosevka Generate is a tool to generate your own [Iosevka][Iosevka] font for you.

[Iosevka][Iosevka] is a fantastic 'for code from code' font, for which all credit goes to [Belleve Invis][Invis] - this repo is merely a helper script to leverage others' hard work.

## Usage

In your `$XDG_CONFIG_HOME` (or `$HOME/.config`) create `iosevka/config`, in INI format such as:
```ini
[options]
    name = myosevka
    sans
    stress-fw
    ligset = haskell

[common]
    l = hooky

[upright]
    q = straight
    zero = slashed

[italic]
    i = hooky
    at = fourfold

[oblique]
    g = opendoublestory
    numbersign = slanted
```

Details of the (growing) options available can be found in the [font's readme][Iosevka].

## Installation

If you clone this repo, you can just create a symbolic link to the contained script somewhere on your `$PATH`:
```sh
ln -s $CLONED_DIR/iosevka-generate /usr/local/bin/iosevka-generate
```

On Arch, use the `PKGBUILD` script in this repo or from the [AUR][aur/iosevka-generate].

On macOS, use the contained brew formula:
```sh
brew install https://raw.githubusercontent.com/OJFord/iosevka-generate/blob/master/iosevka-generate.rb

# Or, from my `brew tap OJFord/formulae`:
brew install OJFord/formulae/iosevka-generate
```

## Licence

The helper tool in this repository is licensed according to the [LICENCE.md](/LICENCE.md) contained within.

This tool retrieves and makes use of the Iosevka font and supporting build tooling, which are copyright of [Belle Invis][Invis] and licensed as described in [that project's repository][Iosevka].


[aur/iosevka-generate]: https://aur.archlinux.org/packages/iosevka-generate
[Invis]: https://github.com/be5invis
[Iosevka]: https://github.com/be5invis/iosevka
