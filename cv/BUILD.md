# Build the CV

From this directory on NixOS:

```sh
nix-shell -p tectonic poppler-utils --run 'tectonic cv.tex'
```

The editable source is `cv.tex`; the output is `cv.pdf`. Fonts are bundled in `resources/fonts`. Tectonic downloads its TeX bundle on the first build.

To render pages for review:

```sh
mkdir -p /tmp/tony-cv-review
nix-shell -p poppler-utils --run 'pdftoppm -png -scale-to 1400 cv.pdf /tmp/tony-cv-review/page'
```
