# Customize and Style Your Terminal

### Tools:
* [Iterm2](https://www.iterm2.com/): alternative to Terminal or Command Prompt
* [Powerlevel9k](https://github.com/bhilburn/powerlevel9k): a theme for ZSH (i.e., basically the true magic behind customizing commands prompts)
* [Oh-My-Zsh](https://ohmyz.sh/): a framework for Z shell (i.e., to cutomize and configure zsh, so your terminal looks pretty
* [Nerd Fonts](https://github.com/ryanoasis/nerd-fonts): provides fonts and glyphs (icons)
* [iTerm2 Color Themes](https://github.com/mbadolato/iTerm2-Color-Schemes): choose any theme of your choice to customize iTerm2 looks

### Prerequisites: 
* install [Homebrew](https://brew.sh/), [iTerm2](https://www.iterm2.com/downloads.html) and [Oh-My-Zsh](https://ohmyz.sh/)

### Follow Through...

#### To Update Oh-My-Zsh
To customize oh-my-zsh, edit ~/.zshrc file, located on your home directory

#### iTerm2 Color Scheme 
To apply a color scheme of iTerm2, refer to its **[installation process]**(https://github.com/mbadolato/iTerm2-Color-Schemes/blob/master/README.md#installation-instructions)

#### Add Custom Font
To add custom fonts or glyphsicons, run: 
```
cd ~/Library/Fonts && curl -fLo "Droid Sans Mono for Powerline Nerd Font Complete.otf" https://github.com/ryanoasis/nerd-fonts/raw/master/patched-fonts/DroidSansMono/complete/Droid%20Sans%20Mono%20Nerd%20Font%20Complete.otf
```
on your terminal or iTerm2

Now, to apply a certain font provided through Nerd Font, go to:
```
iTerm2 -> Preferences -> Profiles -> Text -> Font -> Change Font
```

Then, choose the `Droid Sans Mono Nerd Font Complete` font and set the default font size to 12 or whatever you want

#### Install & Integrate Powerlevel9k with Oh-My-Zsh
To install Powerlevel9k, first choose a safe location in your file system and run: 
```
git clone https://github.com/bhilburn/powerlevel9k.git
```

Now, to tell Powerlevel9k to use the Nerd Fonts in Zsh, run: 
```
echo "POWERLEVEL9K_MODE='nerdfont-complete'" >> ~/.zshrc
```

Then, setup oh-my-zsh to use the Powerlevel9k theme by running... 
```
echo 'source  ~/powerlevel9k/powerlevel9k.zsh-theme' >> ~/.zshrc
```
(Note: we are assuming that powerlevel9k repository has been installed in the root directory, if you install powerlevel9k in a different location, make sure to set proper path, i.e., `echo 'source  ~/dev/powerlevel9k/powerlevel9k.zsh-theme' >> ~/.zshrc`)

#### Now, Configure Powerlevel9k

To customize command prompts, update ~/.zshrc file by adding the following above `source  ~/dev/powerlevel9k/powerlevel9k.zsh-theme`:

```
# Customise the Powerlevel9k prompts
POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(
  custom_medium custom_freecodecamp dir vcs newline status
)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=()
POWERLEVEL9K_PROMPT_ADD_NEWLINE=true

# Add the custom Medium M icon prompt segment
POWERLEVEL9K_CUSTOM_MEDIUM="echo -n '\uF859'"
POWERLEVEL9K_CUSTOM_MEDIUM_FOREGROUND="black"
POWERLEVEL9K_CUSTOM_MEDIUM_BACKGROUND="white"
# Add the custom freeCodeCamp prompt segment

POWERLEVEL9K_CUSTOM_FREECODECAMP="echo -n ’\uE242' freeCodeCamp"
POWERLEVEL9K_CUSTOM_FREECODECAMP_FOREGROUND="white"
POWERLEVEL9K_CUSTOM_FREECODECAMP_BACKGROUND="cyan"
```

Refer to [Show Off Your Config](https://github.com/bhilburn/powerlevel9k/wiki/Show-Off-Your-Config) to find a list of custom config you can use... just copy a config and paste it into your .zshrc file and save.

Now, just restart iTerm2 and check it out!


**Reference**: https://medium.freecodecamp.org/how-you-can-style-your-terminal-like-medium-freecodecamp-or-any-way-you-want-f499234d48bc
