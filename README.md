# MapTiler style guide

[Vale](https://github.com/errata-ai/vale) is an open source prose linter that can check the content of documents in several formats against style guide rules. The goal of a prose linter is automating style guide checks in docs-as-code environments, so it detects style issues before deployment or while you edit documentation in a code editor. 

This repo contains a set of linting rules for Vale based on the Google style guide and MapTiler style guide.

> [!NOTE]
> This repo is a fork of https://github.com/errata-ai/Google. This way, you can synchronize changes to the Google style guide.

## Google style guide

> **NOTE**: This project is neither maintained nor endorsed by Google.

This repository contains a [Vale-compatible](https://github.com/errata-ai/vale) implementation of the [*Google Developer Documentation Style Guide*](https://developers.google.com/style/) ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)).

## Getting started

To get started, add the package to your configuration file (as shown below) and then run `vale sync`.

```ini
StylesPath = vale-styles
MinAlertLevel = suggestion

Packages = https://github.com/maptiler/vale-rules/releases/latest/download/Google.zip, https://github.com/maptiler/vale-rules/releases/latest/download/MapTiler.zip

[*.{md}]
BasedOnStyles = Vale, Google, MapTiler 
```

See [Packages](https://vale.sh/docs/keys/packages) for more information.

## Repository Structure

<dl>
  <dt><a href="https://github.com/maptiler/vale-rules/tree/master/Google"><code>/Google</code></a></dt>
  <dd>The <a href="http://yaml.org/">YAML</a>-based in Google rule implementations with modifications that make up our style.</dd>

  <dt><a href="https://github.com/maptiler/vale-rules/tree/master/MapTiler"><code>/MapTiler</code></a></dt>
  <dd>The <a href="http://yaml.org/">YAML</a>-based in Google rule implementations that make up our style.</dd>

  <dt><a href="https://github.com/errata-ai/Google/tree/master/fixtures"><code>/fixtures</code></a></dt>
  <dd>The individual unit tests. Each directory should be named after a rule found in <code>/Google</code> and include its own <code>.vale.ini</code> file that isolates its target rule.</dd>

  <dt><a href="https://github.com/errata-ai/Google/tree/master/features"><code>/features</code></a></dt>
  <dd>The <a href="https://docs.cucumber.io/cucumber/step-definitions/">Cucumber Step Definitions</a> we use to test our fixtures. Essentially, we use the <a href="https://github.com/cucumber/aruba">aruba</a> framework to test Vale's output after running it on each of our fixture directories.</dd>
</dl>
