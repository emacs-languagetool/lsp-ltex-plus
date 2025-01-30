[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![JCS-ELPA](https://raw.githubusercontent.com/jcs-emacs/badges/master/elpa/v/lsp-ltex-plus.svg)](https://jcs-emacs.github.io/jcs-elpa/#/lsp-ltex-plus)

<img align="right" src="./etc/logo.png" with="115" height="55">

# lsp-ltex-plus
> LSP Clients for LTEX+

[![CI](https://github.com/emacs-languagetool/lsp-ltex-plus/actions/workflows/test.yml/badge.svg)](https://github.com/emacs-languagetool/lsp-ltex-plus/actions/workflows/test.yml)
[![Activate](https://github.com/emacs-languagetool/lsp-ltex-plus/actions/workflows/activate.yml/badge.svg)](https://github.com/emacs-languagetool/lsp-ltex-plus/actions/workflows/activate.yml)

`lsp-mode` client leveraging [LTEX+ Language Server](https://github.com/ltex-plus/ltex-ls-plus).

<p align="center"><img src="./etc/screenshot.png"/></p>

## 💾 Quickstart

```el
(use-package lsp-ltex-plus
  :ensure t
  :hook (text-mode . (lambda ()
                       (require 'lsp-ltex-plus)
                       (lsp)))  ; or lsp-deferred
  :init
  (setq lsp-ltex-plus-version "18.2.0"))  ; make sure you have set this, see below
```

For `lsp-ltex-plus` to run you need to have `ltex-ls-plus` installed and available.
Go to [`ltex-ls-plus` installation page](https://ltex-plus.github.io/ltex-plus/installation-usage.html),
download the appropriate version, uncompress, and place it under
`~/.emacs.d/.cache/lsp/ltex-ls` or `~/.config/emacs/.cache/lsp/ltex-ls`.
As explained there, if you download the archive that corresponds to
your platform, no Java installation is needed. If you use the platform-independent
file, you will need Java in your computer, and you will need to set the JAVA_HOME
environment variable.

In the configuration for `lsp-ltex-plus` you will probably want to set the version
you want to use; for example `(setq lsp-ltex-plus-version "18.2.0")` in the `init`
section of `use-package`.

## 📇 Commands

| Commands                 | Description                                           |
|:-------------------------|:------------------------------------------------------|
| lsp-ltex-plus-upgrade-ls | Upgrade LTEX server, if not found install it instead. |

## 🔧 Configuration

`lsp-ltex-plus` supports following configuration. Each configuration is described in
detail in [LTEX+ Settings](https://ltex-plus.github.io/ltex-plus/settings.html).

* [`ltex.enabled`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexenabled) via `lsp-ltex-plus-enabled`
* [`ltex.language`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexlanguage) via `lsp-ltex-plus-language`
* [`ltex.dictionary`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexdictionary) via `lsp-ltex-plus-dictionary`
* [`ltex.disabledRules`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexdisabledrules) via `lsp-ltex-plus-disabled-rules`
* [`ltex.enabledRules`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexenabledrules) via `lsp-ltex-plus-enabled-rules`
* [`ltex.hiddenFalsePositives`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexhiddenfalsepositives) via `lsp-ltex-plus-hidden-false-positives`
* [`ltex.bibtex.fields`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexbibtexfields) via `lsp-ltex-plus-bibtex-fields`
* [`ltex.latex.commands`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexlatexcommands) via `lsp-ltex-plus-latex-commands`
* [`ltex.latex.environments`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexlatexenvironments) via `lsp-ltex-plus-latex-environments`
* [`ltex.markdown.nodes`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexmarkdownnodes) via `lsp-ltex-plus-markdown-nodes`
* [`ltex.additionalRules.enablePickyRules`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexadditionalrulesenablepickyrules) via `lsp-ltex-plus-additional-rules-enable-picky-rules`
* [`ltex.additionalRules.motherTongue`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexadditionalrulesmothertongue) via `lsp-ltex-plus-mother-tongue`
* [`ltex.additionalRules.languageModel`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexadditionalruleslanguagemodel) via `lsp-ltex-plus-additional-rules-language-model`
* [`ltex.additionalRules.neuralNetworkModel`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexadditionalrulesneuralnetworkmodel) via `lsp-ltex-plus-additional-rules-neural-network-model`
* [`ltex.additionalRules.word2VecModel`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexadditionalrulesword2vecmodel) via `lsp-ltex-plus-additional-rules-word-2-vec-model`
* [`ltex.languageToolHttpServerUri`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexlanguagetoolhttpserveruri) via `lsp-ltex-plus-languagetool-http-server-uri`
* [`ltex.languageToolOrg.username`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexlanguagetoolorgusername) via `lsp-ltex-plus-languagetool-org-username`
* [`ltex.languageToolOrg.apiKey`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexlanguagetoolorgapikey) via `lsp-ltex-plus-languagetool-org-api-key`
* [`ltex.ltex-ls.path`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexltex-lspath) via `lsp-ltex-plus-ls-path`
* [`ltex.ltex-ls.logLevel`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexltex-lsloglevel) via `lsp-ltex-plus-log-level`
* [`ltex.java.path`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexjavapath) via `lsp-ltex-plus-java-path`
* [`ltex.java.initialHeapSize`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexjavainitialheapsize) via `lsp-ltex-plus-java-initial-heap-size`
* [`ltex.java.maximumHeapSize`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexjavamaximumheapsize) via `lsp-ltex-plus-java-maximum-heap-size`
* [`ltex.sentenceCacheSize`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexsentencecachesize) via `lsp-ltex-plus-sentence-cache-size`
* [`ltex.completionEnabled`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexcompletionenabled) via `lsp-ltex-plus-completion-enabled` (currently, not implemented)
* [`ltex.diagnosticSeverity`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexdiagnosticseverity) via `lsp-ltex-plus-diagnostic-severity`
* [`ltex.checkFrequency`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexcheckfrequency) via `lsp-ltex-plus-check-frequency`
* [`ltex.clearDiagnosticsWhenClosingFile`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexcleardiagnosticswhenclosingfile) via `lsp-ltex-plus-clear-diagnostics-when-closing-file`
* [`ltex.statusBarItem`](https://ltex-plus.github.io/ltex-plus/settings.html#ltexstatusbaritem) via `lsp-ltex-plus-status-bar-item` (currently, not implemented)
* [`ltex.trace.server`](https://ltex-plus.github.io/ltex-plus/settings.html#ltextraceserver) via `lsp-ltex-plus-trace-server`

## 🛠️ Contribute

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Elisp styleguide](https://img.shields.io/badge/elisp-style%20guide-purple)](https://github.com/bbatsov/emacs-lisp-style-guide)
[![Donate on paypal](https://img.shields.io/badge/paypal-donate-1?logo=paypal&color=blue)](https://www.paypal.me/jcs090218)
[![Become a patron](https://img.shields.io/badge/patreon-become%20a%20patron-orange.svg?logo=patreon)](https://www.patreon.com/jcs090218)

If you would like to contribute to this project, you may either
clone and make pull requests to this repository. Or you can
clone the project and establish your own branch of this tool.
Any methods are welcome!

### 🔬 Development

To run the test locally, you will need the following tools:

- [Eask](https://emacs-eask.github.io/)
- [Make](https://www.gnu.org/software/make/) (optional)

Install all dependencies and development dependencies:

```sh
$ eask install-deps --dev
```

To test the package's installation:

```sh
$ eask package
$ eask install
```

To test compilation:

```sh
$ eask compile
```

**🪧 The following steps are optional, but we recommend you follow these lint results!**

The built-in `checkdoc` linter:

```sh
$ eask lint checkdoc
```

The standard `package` linter:

```sh
$ eask lint package
```

*📝 P.S. For more information, find the Eask manual at https://emacs-eask.github.io/.*

## ⚜️ License

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <https://www.gnu.org/licenses/>.

See [`LICENSE`](./LICENSE.txt) for details.
