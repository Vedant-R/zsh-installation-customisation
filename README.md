# Zsh Installation, Configuration and Customisation

Zsh download and configure for mac

## Download iTerm

Download the latest [iTerm](http://www.iterm2.com/downloads.html)

## Install oh-my-zsh

Open iTerm and run the command:

```bash
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)
```

## Powerline fonts

Clone, install and remove powerline fonts.

```bash
# clone powerline font repo
git clone https://github.com/powerline/fonts.git --depth=1

# install fonts
cd fonts
./install.sh

# cleanup
cd ..
rm -rf fonts
```

## Configure agnoster theme

- Source: [Agnoster](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes#agnoster).

- Edit `~/.zshrc` to add `agnoster` theme.

```bash
# open zsh config file
vim ~/.zshrc

# update zsh theme section of code
set ZSH_THEME="agnoster"
```

- Take backup of existing agnoster config file and replace it with [agnoster.zsh-theme](agnoster.zsh-theme)

```bash
# backup
cd .oh-my-zsh/themes
mv agnoster.zsh-theme agnoster.zsh-theme_bkp

# either create new or clone and move the above file
mv ~/Downloads/agnoster.zsh-theme .
```

## Customise iTerm

Different customisations for iterm
Source: [Jazz up zsh terminal](https://www.freecodecamp.org/news/jazz-up-your-zsh-terminal-in-seven-steps-a-visual-guide-e81a8fd59a38/)

### iTerm Color Schemes

- Download the [iTerm2-color-schemes](https://github.com/mbadolato/iTerm2-Color-Schemes) as a zip file and extract it.

- The “Schemes” folder contains all the color scheme files — they end with `.itermcolors`.

- Open `iTerm2 > Profiles > Edit Profiles > Colors > Color Presets Drop Down > Import`.

- In the import window, navigate to the “Schemes” folder (from step 2).

- Select all the files so you can import all the color schemes at once.

- Simply select whichever color scheme you like (select `batman`).

### Syntax Highlighting Plugin

- Clone the zsh-syntax-highlighting plugin’s repo and copy it to the “Oh My ZSH” plugins directory.

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

- Activate the plugin in `~/.zshrc` by adding `zsh-syntax-highlighting` to the Plugins section as shown below.

```bash
plugins =(
    git
    zsh-syntax-highlighting
)
```

### ZSH-AutoSuggestion Plugin

- Install.

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

- Activate the plugin in `~/.zshrc` by adding `zsh-autosuggestions` to the Plugins section as shown below.

```bash
plugins =(
    git
    zsh-syntax-highlighting
    zsh-autosuggestions
)
```

### Reflect changes after everything is configured

Re-read zshrc configuration

```bash
source ~/.zshrc
```

### Change iterm fonts

- Open `iTerm2 > Profiles > Edit Profiles > Text > Font Drop Down`.

- Select `Meslo LG L DZ for Powerline`

- Select `Regular` in the next drop down for `font style`.

- Select `14` in the next drop down for `font size`.
