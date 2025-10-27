# qs-plugin-action

This is a custom GitHub Action to build and sign [Quicksilver][0] plugins.

Quicksilver plugins rely on some of the Quicksilver frameworks, so in broad strokes the action:
- clones the latest tagged release of Quicksilver
- builds a Release build of Quicksilver
- uses the `Tools/build-qs-plugin` script in the Quicksilver repository to build the plugin
- uploads an unsigned and signed version of the plugin to the action's outputs
- for tagged releases, a release is created and the plugin is pushed to production
  - the *body* (**excluding** the first line) of the commit message is used as the changelog argument for the `qs-push-plugin` tool

[0]: https://qsapp.com/
