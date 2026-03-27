zsh install
```
sudo apt install zsh
```

make zsh default

```
chsh -s $(which zsh)
```

install a mono font at https://www.nerdfonts.com/font-downloads. My font is `Cascadia Mono`.  Note: font called `CaskaydiyaMono Nerd Font`. (also jetbrains font looks alike)

```
unzip CascadiaMono.zip -d cascadia_font

mkdir -p ~/.local/share/fonts

cp cascadia_font/*.ttf ~/.local/share/fonts/

fc-cache -f -v
```

Font silmek icin

```
kaldir gerekli yerden sonra

fc-cache -f -v
```

oh my zsh install
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

install starship

```
curl -sS https://starship.rs/install.sh | sh
```

add to .zshrc

```
eval "$(starship init zsh)"
```

At this point .zshrc should look like this 

```zsh
# Path to your Oh My Zsh installation.
export ZSH="$HOME/.oh-my-zsh"

# its empty because I use `Starship`
ZSH_THEME=""

plugins=(git)

# Start Oh My Zsh
source $ZSH/oh-my-zsh.sh

# Start Starship; always at the bottom
eval "$(starship init zsh)"
```

Starship configleri komut kosuyoruz. digerleri icin buradan (https://starship.rs/presets/). Ikisi guzel istedigini sec ve kullan. ben simdilik jetpack kullandim

- Jetpack Preset
```
starship preset jetpack -o ~/.config/starship.toml
```

- Pure Preset
```
starship preset pure-preset -o ~/.config/starship.toml
```

Pluginler icin:

/home/ben/.oh-my-zsh/custom/plugins'e gereken pluginleri clone'la `/home/ben/.oh-my-zsh/custom/plugins`
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-substring-search
```

.zshrc guncelle
```
plugins=(
  git
  sudo
  extract
  web-search
  copypath
  colored-man-pages
  history
  zsh-syntax-highlighting
  zsh-autosuggestions
  zsh-history-substring-search
)
```

source it
```
source ~/.zshrc
```

Ghostty install
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/mkasberg/ghostty-ubuntu/HEAD/install.sh)"
```

nano .config/ghostty/config olustur
```
nano ~/.config/ghostty/config
```

icerisine yaz. gecerli olmasi icin tum ghostty instancelerini kapat sonra ac

```
theme = TokyoNight Night

mouse-hide-while-typing = true

gtk-titlebar = false
window-decoration = none

background-opacity = 0.9
background-blur-radius = 10

palette = 1=#B91919
palette = 2=#86D531
palette = 3=#E0A228
palette = 4=#1A55D3
palette = 5=#8558D8
palette = 6=#5DAAD7
palette = 7=#969DBD

# padding
window-padding-x = 10
window-padding-y = 5
window-padding-balance = true
```

>Note: color isleri icin https://www.ditig.com/256-colors-cheat-sheet bak. su sekilde configi guncelleyebilirsin

> Note: starship.toml'da addNewline = False yaparak yukardaki boslugu azaltabilirsin

At the end .zshrc should look like this

```
export ZSH="$HOME/.oh-my-zsh"

# its empty because I use `Starship`
ZSH_THEME=""

plugins=(
  git
  sudo
  extract
  web-search
  copypath
  colored-man-pages
  history
  zsh-syntax-highlighting
  zsh-autosuggestions
  zsh-history-substring-search
)

# Start Oh My Zsh
source $ZSH/oh-my-zsh.sh

# Start Starship; always at the bottom
eval "$(starship init zsh)"
```


