How to Use Closure Linter
================================

This document describes how to install and use Closure Linter.

Install Closure Linter
================================

Use the Python easy_install utility to download and install Closure Linter.

Linux
--------------------------------

To install Closure Linter on Linux, execute the following commands:

`$ cd /tmp
/tmp$ sudo easy_install http://closure-linter.googlecode.com/files/closure_linter-latest.tar.gz`
Mac OS X
--------------------------------

To install Closure Linter on Mac OS X, execute the following command:

`$ sudo easy_install http://closure-linter.googlecode.com/files/closure_linter-latest.tar.gz`
Windows
--------------------------------

To install Closure Linter on Windows:

 - Download and install Python for Windows.
 - Install the Easy Install module.
 - Execute the following command:
 `> easy_install http://closure-linter.googlecode.com/files/closure_linter-latest.tar.gz`

Note: Windows support for Closure Linter is experimental.

Find Style Problems
================================

To run the Closure Linter on a single file, try:

`$ gjslint path/to/my/file.js`

You should see results like this:

```
Line 46, E:0110: Line too long (87 characters).
Line 54, E:0214: Missing description in @return tag
Line 66, E:0012: Illegal semicolon after function declaration
Line 150, E:0120: Binary operator should go on previous line "+"
Line 175, E:0011: Missing semicolon after function assigned to a variable
Line 210, E:0121: Illegal comma at end of array literal
Line 220, E:0002: Missing space before ":"
```

You can also recursively check an entire directory, like this:

`$ gjslint -r path/to/my/directory`

By default, the Closure Linter checks for the presence of correct JsDoc annotations. If you don't want to check for missing JsDoc annotations in your project, disable the check like this:

`$ gjslint --nojsdoc -r path/to/my/directory`

Although this flag disables checks for missing JsDoc annotations, the linter still verifies that existing JsDoc annotations are used correctly.

The `--strict` Flag
--------------------------------

If you want Closure Linter to be more strict about style rules like spacing, JsDoc types, and author tags, use the --strict command line flag. You must use --strict if you are contributing code to the Closure Library.

Fix Style Problems
================================

In any of the above commands, you can substitute fixjsstyle for gjslint to automatically fix many of the errors that gjslint checks for.

For example:

`$ fixjsstyle path/to/file1.js path/to/file2.js`

You should back up your files or store them in a source control system before using fixjsstyle, in case the script makes changes that you don't want.
