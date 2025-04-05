---
project: fnm
stars: 20243
description: 🚀 Fast and simple Node.js version manager, built in Rust
url: https://github.com/Schniz/fnm
---

Fast Node Manager (`fnm`)
=========================

> 🚀 Fast and simple Node.js version manager, built in Rust

Features
--------

🌎 Cross-platform support (macOS, Windows, Linux)

✨ Single file, easy installation, instant startup

🚀 Built with speed in mind

📂 Works with `.node-version` and `.nvmrc` files

Installation
------------

### Using a script (macOS/Linux)

For `bash`, `zsh` and `fish` shells, there's an automatic installation script.

First ensure that `curl` and `unzip` are already installed on you operating system. Then execute:

curl -fsSL https://fnm.vercel.app/install | bash

#### Upgrade

On macOS, it is as simple as `brew upgrade fnm`.

On other operating systems, upgrading `fnm` is almost the same as installing it. To prevent duplication in your shell config file, pass `--skip-shell` to the install command:

curl -fsSL https://fnm.vercel.app/install | bash -s -- --skip-shell

#### Parameters

`--install-dir`

Set a custom directory for fnm to be installed. The default is `$XDG_DATA_HOME/fnm` (if `$XDG_DATA_HOME` is not defined it falls back to `$HOME/.local/share/fnm` on linux and `$HOME/Library/Application Support/fnm` on MacOS).

`--skip-shell`

Skip appending shell specific loader to shell config file, based on the current user shell, defined in `$SHELL`. e.g. for Bash, `$HOME/.bashrc`. `$HOME/.zshrc` for Zsh. For Fish - `$HOME/.config/fish/conf.d/fnm.fish`

`--force-install`

macOS installations using the installation script are deprecated in favor of the Homebrew formula, but this forces the script to install using it anyway.

Example:

curl -fsSL https://fnm.vercel.app/install | bash -s -- --install-dir "./.fnm" --skip-shell

### Manually

#### Using Homebrew (macOS/Linux)

brew install fnm

Then, set up your shell for fnm

#### Using Winget (Windows)

winget install Schniz.fnm

#### Using Scoop (Windows)

scoop install fnm

Then, set up your shell for fnm

#### Using Chocolatey (Windows)

choco install fnm

Then, set up your shell for fnm

#### Using Cargo (Linux/macOS/Windows)

cargo install fnm

Then, set up your shell for fnm

#### Using a release binary (Linux/macOS/Windows)

-   Download the latest release binary for your system
-   Make it available globally on `PATH` environment variable
-   Set up your shell for fnm

### Removing

To remove fnm (😢), just delete the `.fnm` folder in your home directory. You should also edit your shell configuration to remove any references to fnm (ie. read Shell Setup, and do the opposite).

Completions
-----------

fnm ships its completions with the binary:

fnm completions --shell <SHELL\>

Where `<SHELL>` can be one of the supported shells:

-   `bash`
-   `zsh`
-   `fish`
-   `powershell`

Please follow your shell instructions to install them.

### Shell Setup

Environment variables need to be setup before you can start using fnm. This is done by evaluating the output of `fnm env`.

Note

Check out the Configuration section to enable highly recommended features, like automatic version switching.

Adding a `.node-version` to your project is as simple as:

$ node --version
v14.18.3
$ node --version \> .node-version

Check out the following guides for the shell you use:

#### Bash

Add the following to your `.bashrc` profile:

eval "$(fnm env --use-on-cd --shell bash)"

#### Zsh

Add the following to your `.zshrc` profile:

eval "$(fnm env --use-on-cd --shell zsh)"

#### Fish shell

Create `~/.config/fish/conf.d/fnm.fish` and add this line to it:

fnm env \--use-on-cd \--shell fish | source

#### PowerShell

Add the following to the end of your profile file:

fnm env \--use-on\-cd \--shell powershell | Out-String | Invoke-Expression

-   For macOS/Linux, the profile is located at `~/.config/powershell/Microsoft.PowerShell_profile.ps1`
-   For Windows location is either:
    -   `%userprofile%\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1` Powershell 5
    -   `%userprofile%\Documents\PowerShell\Microsoft.PowerShell_profile.ps1` Powershell 6+
-   To create the profile file you can run this in PowerShell:
    
    if (\-not (Test-Path $profile)) { New-Item $profile \-Force }
    
-   To edit your profile run this in PowerShell:
    
    Invoke-Item $profile
    

#### Windows Command Prompt aka Batch aka WinCMD

fnm is also supported but is not entirely covered. You can set up a startup script for cmd.exe or Windows Terminal and append the following lines:

@echo off
:: for /F will launch a new instance of cmd so we create a guard to prevent an infnite loop
if not defined FNM\_AUTORUN\_GUARD (
    set "FNM\_AUTORUN\_GUARD\=AutorunGuard"
    FOR /f "tokens=\*" %%z IN ('fnm env --use-on-cd') DO CALL %%z
)

#### Usage with Cmder

Usage is very similar to the normal WinCMD install, apart for a few tweaks to allow being called from the cmder startup script. The example **assumes** that the `CMDER_ROOT` environment variable is **set** to the **root directory** of your Cmder installation. Then you can do something like this:

-   Make a .cmd file to invoke it

:: %CMDER\_ROOT%\\bin\\fnm\_init.cmd
@echo off
FOR /f "tokens=\*" %%z IN ('fnm env --use-on-cd') DO CALL %%z

-   Add it to the startup script

:: %CMDER\_ROOT%\\config\\user\_profile.cmd
call "%CMDER\_ROOT%\\bin\\fnm\_init.cmd"

You can replace `%CMDER_ROOT%` with any other convenient path too.

Configuration
-------------

See the available configuration options for an extended configuration documentation

Usage
-----

See the available commands for an extended usage documentation

Contributing
------------

PRs welcome 🎉

### Developing:

# Install Rust
git clone https://github.com/Schniz/fnm.git
cd fnm/
cargo build

### Running Binary:

cargo run -- --help # Will behave like \`fnm --help\`

### Running Tests:

cargo test
