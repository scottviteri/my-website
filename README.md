# Scott Viteri's website

This is the Hugo source for [scottviteri.com](https://scottviteri.com/).

## Repository layout

- This repository contains the site's source content, configuration, layouts,
  and static assets.
- `themes/academic` is a vendored copy of the legacy Academic theme. It is
  tracked as ordinary files, not as a Git submodule. The old theme is still
  part of the working site; upgrading it should be treated as a separate
  migration.
- `public` is the only Git submodule. It points to
  [`scottviteri/scottviteri.github.io`](https://github.com/scottviteri/scottviteri.github.io),
  which contains the generated site.
- GitHub Pages serves the root of the output repository's `master` branch. The
  source repository itself is not a Pages site.

This intentionally separates editable source from generated output:

```text
my-website (Hugo source)
    | hugo
    v
public/ (submodule / generated files)
    | push
    v
scottviteri.github.io master -> GitHub Pages -> scottviteri.com
```

## Local setup

Clone the source and initialize the generated-output submodule:

```sh
git clone git@github.com:scottviteri/my-website.git
cd my-website
git submodule update --init public
```

The Academic theme is already included in the source checkout. Do not try to
initialize it as a submodule.

## Build and preview

An extended Hugo installation is required. The theme is old, so verify the
site before changing Hugo or theme versions.

```sh
hugo server
```

For a production build into the initialized output submodule:

```sh
hugo
```

Before publishing, inspect both repositories independently:

```sh
git status --short
git -C public status --short
```

## Publish

Publishing is a two-repository operation. First commit and push the generated
files in the output repository; then record the new output commit in the source
repository:

```sh
git -C public add -A
git -C public commit -m "Update generated site"
git -C public push origin master

git add public
git commit -m "Update generated site pointer"
git push origin master
```

The source repository does not run a Pages deployment workflow. This avoids a
second deployment mechanism competing with the output repository that actually
owns the live Pages configuration.
