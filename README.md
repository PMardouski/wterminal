# Customize Windows Terminal

## This is simple instruction on how to tune the Windows Terminal

As you know using the CMD command the Console Prompt app is launched by default, in case we want to change this behaviour we need to switch _Windows Console Host_ to _Windows Terminal_ the from default terminal application setting menu in Windows Terminal as on the screenshot below:

:bangbang: **<span style="color:red">IMPORTANT:</span> this option is available only for PCs with Windows 11 operating system installed**

![](/img/TerminalSettings.png)

Setup last stable version of PowerShell using Store:

![](/img/PowerShell_setup.png)

<p>How setting up a menu nave bar in weindows terminal?</p>
<p>the first thing we may need to customize the profile JSON section (to hide Windows PowerShell, and move up the installed erlier PowerShell):</p>

``` json
"profiles": {
  "defaults": {},
  "list":
  [
      {
          "commandline": "powershell.exe",
          "guid": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
          "hidden": true,
          "name": "Windows PowerShell"
      },
      {
          "guid": "{574e775e-4f2a-5b96-ac1e-a2962a402336}",
          "hidden": false,
          "name": "PowerShell",
          "source": "Windows.Terminal.PowershellCore"
      },
      {
          "commandline": "cmd.exe",
          "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
          "hidden": false,
          "name": "Command Prompt"
      },
      {
          "guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b8}",
          "hidden": false,
          "name": "Azure Cloud Shell",
          "source": "Windows.Terminal.Azure"
      },
      {
          "guid": "{2ece5bfe-50ed-5f3a-ab87-5cd4baafed2b}",
          "hidden": false,
          "name": "Git Bash",
          "source": "Git"
      }
  ]
}
```

## How to Install WSL

<p>the next step is Install the WSL, you may do it using next command:</p>

`wsl --install`

### Setup linux 'Ubuntu'

![](/img/SetupLinuxUbuntu.png)

then custommize setting.json file, change Ubuntu section like on example below:

```json
{
  "backgroundImage": "D:\\Dropbox\\utils\\TerminalBackgrounds\\ubuntu_white-orange_hex_su.png",
  "backgroundImageAlignment": "bottomRight",
  "backgroundImageStretchMode": "none",
  "colorScheme": "UbuntuLegit",
  "guid": "{c6eaf9f4-32a7-5fdc-b5cf-066e8a4b1e40}",
  "hidden": false,
  "name": "Ubuntu-18.04",
  "source": "Windows.Terminal.Wsl",
  "startingDirectory": "//wsl$/Ubuntu-18.04/home/[uer_name]"
}
```

<p>

:memo: in some cases you may need to update a `startingDirectory` value with `//wsl$/Ubuntu/home/[uer_name]`

</p>
<p>

also you may improve this flow with next JSON example:
```json
{
  "guid": "{c6eaf9f4-32a7-5fdc-b5cf-066e8a4b1e40}",
  "name": "Ubuntu",
  "source": "Windows.Terminal.Wsl",
  "commandLine": "wsl ~"
}
```

</p>

## Tune a font
<p>

for customizing terminal font we will use the [NerdFonts](http://nerdfonts.com),
click Download section and find/navigate to _Caskaydia Cove Nerd Font_, please download it and unzip.

</p>

![](/img/CaskaydiaCoveNerdFont.png)

aftar that copy all files and paset to `C:\Windows\Fonts`

then go to site [OhmyPosh](https://ohmyposh.dev/docs/windows) and following the instraction on the page settup OhMyPosh or use next solution:

- use command to install OhMyPosh `winget install JanDeDobbeleer.OhMyPosh`
- restart terminal and use `oh-my-posh.exe` as command to verify that OhMyPosh is working

However, you may figure out that font is displyed incorrect with encoding characters like on screen beow:

![](/img/OhMyPosh_first_run.png)

Open Terminal settings, navigate to `PowerShell/Appearance/Font` and find `CascaydiaCove NF`, save changes:

![](/img/ChangeTerminalFont.png)
