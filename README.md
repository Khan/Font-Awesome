#[Font Awesome v3.2.1](http://fontawesome.io)
###the iconic font designed for Bootstrap

Font Awesome is a full suite of 361 pictographic icons for easy scalable vector graphics on websites, created and
maintained by [Dave Gandy](http://twitter.com/davegandy). Stay up to date [@fontawesome](http://twitter.com/fontawesome).

Get started at http://fontawesome.io!

##License
- The Font Awesome font is licensed under the SIL OFL 1.1:
  - http://scripts.sil.org/OFL
- Font Awesome CSS, LESS, and SASS files are licensed under the MIT License:
  - http://opensource.org/licenses/mit-license.html
- The Font Awesome documentation is licensed under the CC BY 3.0 License:
  - http://creativecommons.org/licenses/by/3.0/
- Attribution is no longer required as of Font Awesome 3.0, but much appreciated:
  - `Font Awesome by Dave Gandy - http://fontawesome.io`
- Full details: http://fontawesome.io/license

##Changelog
- v3.0.0 - all icons redesigned from scratch, optimized for Bootstrap's 14px default
- v3.0.1 - much improved rendering in webkit, various bug fixes
- v3.0.2 - much improved rendering and alignment in IE7
- v3.1.0 - Added 54 icons, icon stacking styles, flipping and rotating icons, removed SASS support
- [v3.1.1 GitHub milestones](https://github.com/FortAwesome/Font-Awesome/issues?milestone=4&page=1&state=closed)
- [v3.2.0 GitHub milestones](https://github.com/FortAwesome/Font-Awesome/issues?milestone=3&page=1&state=closed)
- [v3.2.1 GitHub milestones](https://github.com/FortAwesome/Font-Awesome/issues?milestone=5&page=1&state=closed)

##Versioning

Font Awesome will be maintained under the Semantic Versioning guidelines as much as possible. Releases will be numbered with the following format:

`<major>.<minor>.<patch>`

And constructed with the following guidelines:

* Breaking backward compatibility bumps the major (and resets the minor and patch)
* New additions, including new icons, without breaking backward compatibility bumps the minor (and resets the patch)
* Bug fixes and misc changes bumps the patch

For more information on SemVer, please visit http://semver.org.

##Author
- Email: dave@fontawesome.io
- Twitter: http://twitter.com/davegandy
- GitHub: https://github.com/davegandy
- Work: Lead Product Designer @ http://kyru.us

## Hacking on Font Awesome

From the root of the repository, install the tools used to develop.

    $ bundle install
    $ npm install

Build the project and documentation:

    $ bundle exec jekyll build

Or serve it on a local server on http://localhost:7998/Font-Awesome/:

    $ bundle exec jekyll serve

## Developing more glyphs and building the font

In order to continue adding new glyphs to fontawesome while also retaining the ability to merge in changes from upstream fontawesome, all glyphs that we add should be in the `0xF300-0xF4FF` range of the PUA. this means that our glyphs will always show up sorted after the regular fontawesome glyphs.

To start hacking on the font, crack open your editor of choice and work on `font/FontAwesome.ufo`. Having made your glyph, you should proceed to update the following files:

* [ ] update `src/icons.yml` with your new glyph and unicode point
* [ ] generate the font in `src/assets/font-awesome/font/`

* generate the following fonts:
* [ ] FontAwesome.otf, a cff opentype font
* [ ] fontawesome-webfont.ttf
* [ ] fontawesome-webfont.eot
* [ ] fontawesome-webfont.woff
* [ ] fontawesome-webfont.svg

in the project root, you can *now* do
```
    bundle exec jekyll build
    bundle exec jekyll serve
```

the files that this generates are placed in `$ROOT/less/` and in `$ROOT/font/`. you can copy the fonts into our project's `/fonts` folder and the less files can go in `/stylesheets/fontawesome-package/`

## Generating webfonts

what a pain, but there are two options: the first is fontsquirrel. if you go this route you must not allow it to subset the webfont at all. since fontawesome's glyphs are all in the private use area, subsetting would cause no glyphs to be output.

there's also FontPrep, a $5 mac app which takes care of doing this locally, but you need to rename everything.
