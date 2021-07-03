# ✨Enhancing Windows Terminal experience

If you are using Windows and Linux both for development, wouldn't it be nice to have same terminal experience like Linux terminal (which allows with tons of configurations 😁) without need of installing a new [Terminal](https://www.puttygen.com/windows-terminal-emulators).

> My personal favorite 3rd party terminal is Hyper 🤫

## Okay, so how it's possible? 🤔

Before we get into that, we need to ask why we needed to install new terminal?
Because we needed configurable GUI which windows command prompt is not. But there is another console available on windows i.e. `Powershell` which more powerful than `cmd` by allowing scripting and modules.

## How to do it? 😍

Windows Terminal already allows visual customizations like color scheme but what we need is custom `Prompt String` and `Aliases`.

### How to customize Prompt string?

Fortunately, it's easy to customize prompt string with just one module for PowerShell. We are going to install module called [oh-my-posh](https://ohmyposh.dev).

To install this module, you need run following command in PowerShell -

```
Install-Module oh-my-posh -Scope CurrentUser
```

After installing it, we need to enable it by importing it and setting a theme. To do that we need to add following command to PowerShell profile

```
Import-Module oh-my-posh
Set-PoshPrompt -Theme robbyrussel
```

> PowerShell profile can be open with command `code $PROFILE` if you are using VSCode or replace `code` with your preferred text editor

Now just reload PowerShell profile and see magic. If you have any issues with installation head over to [Oh My Posh docs](https://ohmyposh.dev/docs/pwsh).

### How to set aliases?

Since PowerShell allows scripting hence it's easy to setup aliases even more complex aliases. Aliases are added to same PowerShell profile `$PROFILE` that we just added oh-my-posh module to it.

Aliases in PowerShell are set with following command

```typescript
function Function-Name {
    //anything
    //e.g. git add $args
}
New-Alias -Name <Aliase> -Value <Function-Name>
```

For `options/arguments` available while setting aliases or more information on this head over to PowerShell aliases [docs](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/set-alias).

> [ThatRubenAguilar](https://gist.github.com/ThatRubenAguilar) has build awesome git aliases, you can find it [here](https://gist.github.com/ThatRubenAguilar/85670a6948c6bec777ddaa2b1e8f5cca) and customize to your need.
