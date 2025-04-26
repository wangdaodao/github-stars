---
project: emmet-sublime
stars: 5245
description: Emmet for Sublime Text
url: https://github.com/sergeche/emmet-sublime
---

This plugin is deprecated and no longer maintained, please use new version.
===========================================================================

* * *

Emmet for Sublime Text
======================

Official Emmet plugin for Sublime Text.

-   How to install
-   Available actions
-   Extensions support
-   Overriding keyboard shortcuts
-   How to expand abbreviatoins with Tab key in other syntaxes
-   Notes about Tab key handler

How to install
--------------

_Warning:_ this plugin may not work at all in some OSes since it written in JavaScript and uses PyV8 and Google V8 binaries to run. If you experience problems or editor crashes please fill an issue.

With Package Control:

1.  Run “Package Control: Install Package” command, find and install `Emmet` plugin.
2.  Restart ST editor (if required)

Manually:

1.  Clone or download git repo into your packages folder (in ST, find Browse Packages... menu item to open this folder)
2.  Restart ST editor (if required)

* * *

**WARNING**: When plugin is installed, it will automatically download required PyV8 binary so you have to wait a bit (see _Loading PyV8 binary_ message on status bar). If you experience issues with automatic PyV8 loader, try to install it manually.

Available actions
-----------------

-   Expand Abbreviation – Tab or Ctrl+E
-   Interactive “Expand Abbreviation” — Ctrl+Alt+Enter
-   Match Tag Pair Outward – ⌃D (Mac) / Ctrl+, (PC)
-   Match Tag Pair Inward – ⌃J / Shift+Ctrl+0
-   Go to Matching Pair – ⇧⌃T / Ctrl+Alt+J
-   Wrap With Abbreviation — ⌃W / Shift+Ctrl+G
-   Go to Edit Point — Ctrl+Alt+→ or Ctrl+Alt+←
-   Select Item – ⇧⌘. or ⇧⌘, / Shift+Ctrl+. or Shift+Ctrl+,
-   Toggle Comment — ⇧⌥/ / Shift+Ctrl+/
-   Split/Join Tag — ⇧⌘' / Shift+Ctrl+\`
-   Remove Tag – ⌘' / Shift+Ctrl+;
-   Update Image Size — ⇧⌃I / Ctrl+U
-   Evaluate Math Expression — ⇧⌘Y / Shift+Ctrl+Y
-   Reflect CSS Value – ⇧⌘R / Shift+Ctrl+R
-   Encode/Decode Image to data:URL – ⇧⌃D / Ctrl+'
-   Rename Tag – ⇧⌘K / Shift+Ctrl+'

Increment/Decrement Number actions:

-   Increment by 1: Ctrl+↑
-   Decrement by 1: Ctrl+↓
-   Increment by 0.1: Alt+↑
-   Decrement by 0.1: Alt+↓
-   Increment by 10: ⌥⌘↑ / Shift+Alt+↑
-   Decrement by 10: ⌥⌘↓ / Shift+Alt+↓

Extensions support
------------------

You can easily extend Emmet with new actions and filters or customize existing ones. In `Emmet.sublime-settings`, define `extensions_path` setting and Emmet will load all `.js` and `.json` files in specified folder at startup.

The default value of `extensions_path` is `~/emmet`, which points to _emmet_ folder inside your OS user’s home folder.

Also, you can create sections named as extension files (e.g. `snippets`, `preferences` and `syntaxProfiles`) inside user’s `Emmet.sublime-settings` file and write your customizations there. See original settings file for examples.

Overriding keyboard shortcuts
-----------------------------

Sublime Text is a great text editor with lots of features and actions. Most of these actions are bound to keyboard shortcuts so it’s nearly impossible to provide convenient plugin shortcuts for third-party plugins.

If you’re unhappy with default keymap, you can disable individual keyboard shortcuts with `disabled_keymap_actions` preference of `Emmet.sublime-settings` file.

Use a comma-separated list of action names which default keyboard shortcuts should be disabled. For example, if you want to release Ctrl+E (“Expand Abbreviation”) and Ctrl+U (“Update Image Size”) shortcuts, your must set the following value:

```
"disabled_keymap_actions": "expand_abbreviation, update_image_size"
```

You should refer `Default (Your-OS-Name).sublime-keymap` file to get action ids (look for `args/action` key).

To disable all default shortcuts, set value to `all`:

```
"disabled_keymap_actions": "all"
```

Not that if you disabled any action like so and you’re create your own keyboard shortcut, you **should not** use `emmet_action_enabled.ACTION_NAME` context since this is the key that disables action.

How to expand abbreviations with Tab in other syntaxes
------------------------------------------------------

Emmet expands abbreviations in limited syntaxes only: HTML, CSS, LESS, SCSS, Stylus and PostCSS. The reason to restrict Tab handler to a limited syntax list is because it breaks native Sublime Text snippets.

If you want to abbreviation with Tab in other syntaxes (for example, JSX, HAML etc.) you have to tweak your keyboard shorcuts settings: add `expand_abbreviation_by_tab` command for `tab` key for required syntax _scope selectors_. To get current syntax scope selector, press ⇧⌃P (OSX) or Ctrl+Alt+Shift+P, it will be displayed in editor status bar.

Go to `Preferences` > `Key Bindings — User` and insert the following JSON snippet with properly configured scope selector instead of `SCOPE_SELECTOR` token:

{
  "keys": \["tab"\], 
  "command": "expand\_abbreviation\_by\_tab", 

  // put comma-separated syntax selectors for which 
  // you want to expandEmmet abbreviations into "operand" key 
  // instead of SCOPE\_SELECTOR.
  // Examples: source.js, text.html - source
  "context": \[
    {
      "operand": "SCOPE\_SELECTOR", 
      "operator": "equal", 
      "match\_all": true, 
      "key": "selector"
    }, 

    // run only if there's no selected text
    {
      "match\_all": true, 
      "key": "selection\_empty"
    },

    // don't work if there are active tabstops
    {
      "operator": "equal", 
      "operand": false, 
      "match\_all": true, 
      "key": "has\_next\_field"
    }, 

    // don't work if completion popup is visible and you
    // want to insert completion with Tab. If you want to
    // expand Emmet with Tab even if popup is visible -- 
    // remove this section
    {
      "operand": false, 
      "operator": "equal", 
      "match\_all": true, 
      "key": "auto\_complete\_visible"
    }, 
    {
      "match\_all": true, 
      "key": "is\_abbreviation"
    }
  \]
}

### Tab key handler

Emmet plugin allows you to expand abbreviations with Tab key, just like regular snippets. On the other hand, due to dynamic nature and extensive syntax, sometimes you may get unexpected results. This section describes how Tab handler works and how you can fine-tune it.

By default, Tab handler works in a limited _syntax scopes_: HTML, XML, HAML, CSS, SASS/SCSS, LESS, PostCSS and _strings in programming languages_ (like JavaScript, Python, Ruby etc.). It means:

-   You have to switch your document to one of the syntaxes listed above to expand abbreviations by Tab key.
-   With Ctrl-E shortcut, you can expand abbreviations everywhere, its scope is not limited.
-   When you expand abbreviation inside strings of programming languages, the output is generated with special output profile named `line` that generates output as a single line.

To fine-tune Tab key handler, you can use the following settings in user’s `Emmet.sublime-settings` file:

-   `disable_tab_abbreviations_for_scopes` — a comma-separated list of syntax scopes where Tab key handler should be disabled. For example, if you want disable handler inside strings of programming languages and HAML syntax, your setting will look like this:

"disable\_tab\_abbreviations\_for\_scopes": "text.haml, string"

-   `disabled_single_snippet_for_scopes` — a comma-separated list of syntax scopes where Tab handler should be disabled when expanding a single abbreviation. Currently, ST doesn’t provide API for getting list of native snippets. So, for example, if you try to expand a `php` abbreviation, it will be passed to Emmet which outputs `<php></php>` instead of PHP block as defined in native ST snippets. As a workaround, if you’re trying to expand a single abbreviation inside scope defined in `disabled_single_snippet_for_scopes` setting Emmet will look for its name inside its own snippets catalog first, inside `known_html_tags` setting second and if it’s not found, it allows ST to handle it and expand native abbreviation, if matched.
-   `known_html_tags` — a space-separated list of all known HTML tags used for lookup as described above.

If you’re unhappy with Emmet tab handler behavior, you can disable it: just add `"disable_tab_abbreviations": true` into user’s `Preferences.sublime-settings` file.

Disable automatic vendor prefixes insertion
-------------------------------------------

If your workflow already includes an automated task for CSS vendor prefixing (such as Autoprefixer), you can disable Emmet's automatic vendor prefixes insertion adding this option to your user’s `Emmet.sublime-settings` file:

{
  "preferences": {
    "css.autoInsertVendorPrefixes": false
  }
}
