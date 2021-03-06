## Version 0.5.0 (unreleased)

- Fewer GHC extensions required

## Version 0.4.1 (04 Sep 2012)

- Fixed bugs
    * \#19 - Regression

## Version 0.4.0 (05 Aug 2012)

- Brief help text for nested commands now shows the full command line.

- Fixed inefficiency in the `arguments` parsers for long argument lists.

- Added automatic [bash
completion](https://github.com/pcapriotti/optparse-applicative/wiki/Bash-Completion).

- Added `disambiguate` modifier for `prefs`, which enabled automatic
disambiguation of option abbreviations. With disambiguation on, a command line
like:

        foo --out

  will match an option called `--output`, as long as its the only one starting
  with the string `out`.

- Added `briefDesc` modifier.

- Fixed bugs
    * \#8 - Long options not disambiguated
    * \#10 - Shell completions
    * \#12 - Possible memory leak?

## Version 0.3.2 (31 Jul 2012)

- Fixed bug where both branches of an alternative could be matched.

- Improved brief help text for alternatives.

## Version 0.3.1 (30 Jul 2012)

- Added new `showDefault` and `showDefaultWith` modifiers, which will result in
the default value (if present) to be displayed in the help text.

- Fixed bugs
    * \#12 - Optionally display default values in help

## Version 0.3.0 (30 Jul 2012)

- Option modifiers are now instances of `Monoid` instead of `Category`.

- Dropped dependencies on data-default and data-lens.

- Fixed bugs
    * \#14 - "arguments" can no longer take a list as a default

## Version 0.2.0 (23 Jul 2012)

- Parser is now an instance of Alternative. This makes it possible to build
certain complex parsers that were not definable before. See
`tests/Examples/Alternatives.hs` for a simple example.

- Removed `multi` modifier. You can now use the `many` or `some` methods from
`Alternative`, instead, to create parsers for options that can appear more than
once.

- Added new `flag'` builder that returns a flag without a default value.
Although flags without default values were not useful before, with the addition
of `Alternative` combinators, they do have valid use cases.

- Added new `internal` modifier for options. An internal option is completely
invisible in the help text.

- Added a new `customExecParser` function, which takes an additional
`ParserPrefs` parameter. At the moment, `ParserPrefs` can only be used to
control how many-valued option metavars are displayed in the help text. Setting
its `multiSuffix` field to e.g. `...` will result in an `arguments` parser
description like `[METAVAR]...`.

- Fixed bugs
    * \#6 - "arguments" swallows options
    * \#5 - Help formatting for "arguments" misleading

## Version 0.1.1 (21 Jul 2012)

- New arrow interface

- Fixed bugs
      * \#7 - "arguments" reads positional arguments in reverse

## Version 0.1.0 (07 Jul 2012)

- Improved error reporting internals

- Removed template-haskell dependency

- Fixed bugs:
      * \#3 - No help for subparsers
      * \#4 - Extra empty lines around command list

## Version 0.0.1 (09 Jun 2012)

- Initial release.
