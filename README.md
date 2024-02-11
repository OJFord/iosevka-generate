# Iosevka Generate

Iosevka Generate is a tool to generate your own [Iosevka][Iosevka] font for you.

[Iosevka][Iosevka] is a fantastic 'for code from code' font, for which all credit goes to [Belleve Invis][Invis] - this repo is merely a helper script to leverage others' hard work.

NB: Iosevka itself now has a TOML spec for font building, which can now be used as the input to `iosevka-generate`. The remaining added value is:
  - handle acquiring & installing repo and dependencies automatically
  - similarly auto-storing/re-caching the generated font
  - patch with [nerd font][NerdFont] (currently in INI format only, cf. #8)

## Usage

In your `$XDG_CONFIG_HOME` (or `$HOME/.config`) create `iosevka/my-font.toml` in Iosevka's 'private-build-plans' TOML format (recommended), or `iosevka/config.ini` in INI format (which may be removed in the future) such as:
```ini
[options]
    name = myosevka
    serifs = sans
    ligset = haskell
    nerdfont = fontawesome powerline material octicons

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

This format is kept only for backwards compatibility - it is recommended to use [`private-build-plans.toml` format](https://github.com/be5invis/Iosevka/blob/main/doc/custom-build.md) now that it exists; which supports many more options than our INI format ever did, such as restricting widths/weights (helpful to reduce build time for a monospace/term only font).

In the TOML format, nerdfont options can be specified with an `iosevka-generate` options section:
```toml
[buildPlans.myosevka.iosevka-generate]
nerdfont = ["fontawesome", "powerline", "material", "octicons"]
```

For the rest of the (upstream) options, [Iosevka Customizer](https://typeof.net/Iosevka/customizer) is a handy tool to generate the plan visually, or even just to familiarise yourself with the format and sorts of options available.

## Installation

If you clone this repo, you can just create a symbolic link to the contained script somewhere on your `$PATH`:
```sh
ln -s $CLONED_DIR/iosevka-generate /usr/local/bin/iosevka-generate
```

On Arch, use the `PKGBUILD` script in this repo or from the [AUR][aur/iosevka-generate].

On macOS, use the brew formula:
```sh
brew install OJFord/formulae/iosevka-generate
```

## Licence

The helper tool in this repository is licensed according to the [LICENCE.md](/LICENCE.md) contained within.

This tool retrieves and makes use of the Iosevka font and supporting build tooling, which are copyright of [Belle Invis][Invis] and licensed as described in [that project's repository][Iosevka].

Nerd Font is (optionally) used for patching additional glyphs, and is copyright of [Ryan L. McIntyre][McIntyre] and licensed as described in [that project's repository][NerdFont].


[aur/iosevka-generate]: https://aur.archlinux.org/packages/iosevka-generate
[Invis]: https://github.com/be5invis
[Iosevka]: https://github.com/be5invis/iosevka
[NerdFont]: https://github.com/ryanoasis/nerd-fonts
[McIntyre]: https://github.com/ryanoasis
