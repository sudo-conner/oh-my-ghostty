# Upgrading My Terminal Experience

So, I have to admit... I've been using the default terminal in macOS (Terminal.app) for the past few years.
There's nothing *wrong* with it if you just need to get a couple things done — but there's also nothing special about it.
Terminal.app doesn't come with many features or customization options, and performance can be lacking compared to other terminal emulators.

I started looking for another option and came across [Ghostty](https://ghostty.org/).
Ghostty was created by [Mitchell Hashimoto](https://mitchellh.com/), former co-founder of [HashiCorp](https://www.hashicorp.com/), and was recently released to the public.

> Ghostty is a terminal emulator that differentiates itself by being fast, feature-rich, and native. While there are many excellent terminal emulators available, they all force you to choose between speed, features, or native UIs. Ghostty provides all three.

That's what Mitchell says about Ghostty, and all the reviews I found seemed to agree.
Lots of people have been pretty excited about this project and I was feeling ready to jump in!

## Getting Started

First let's take a moment to remember what we're leaving behind. 🫡

![mac default terminal](/pics/mac-default-terminal.png)

You've served me well, just not that well. Hopefully you won't be missed, Terminal.app.

Time to move on: 
- Download Ghostty from the website or use Homebrew:

```bash
brew install --cask ghostty
```

- Add a theme to the config file:

```bash
theme = catppuccin-frappe
```

- Profit $$$

Here's what we got after just a couple steps:

![ghostty](/pics/ghostty-1.png)

Okay that's not *that* different than before, but we're not done with the cosmetic upgrades!

## Oh My ZSH!

Of course we're installing Oh My ZSH. 
- Go to [Oh My ZSH GitHub](https://github.com/ohmyzsh/ohmyzsh)
- Use their `curl` or `wget` command:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

- Configure how you like!

![oh my zsh](/pics/ghostty-2.png)

## Powerlevel10k

[Powerlevel10k](https://github.com/romkatv/powerlevel10k) is a very popular theme for ZSH. While there are other alternatives out there, this one is widely adopted, well-documented, and easy to configure — so I gave it a try.

There are a handful of ways to install P10K; I used Homebrew:

```bash
brew install powerlevel10k
```

Homebrew provides the path to the theme, which needs to be added to your `.zshrc` file.

![powerlevel10k](/pics/powerlevel10k.png)

Once that's done, restart Ghostty and run through the P10K setup wizard.
- Choose your preferences at each menu

![p10k wizard 1](/pics/p10k-wizard-1.png)

Here's what I decided on. Nice and clean.

![p10k](/pics/p10k.png)

## Other Quality of Life Tools

### Fastfetch

Let’s be honest — customizing your terminal isn’t complete until you post a screenshot of Neofetch or Fastfetch.

```bash
brew install fastfetch
```

![homebrew fastfetch](/pics/homebrew-fastfetch.png)

Finally, what we've all been waiting for...

![fastfetch](/pics/fastfetch.png)

Beautiful, isn't it?

### Syntax Highlighting + Autosuggestions

Okay, that's probably enough cosmetic upgrades.
Syntax highlighting and autosuggestions actually make the terminal easier to use. 

Syntax highlighting helps you catch typos or missing commands before you hit enter.
Autosuggestions show a grayed-out suggestion based on your history as you type.

Install both with Homebrew:

```bash
brew install zsh-syntax-highlighting
brew install zsh-autosuggestions
```

Then add them to your .zshrc:

```bash
source $(brew --prefix)/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
source $(brew --prefix)/share/zsh-autosuggestions/zsh-autosuggestions.zsh
```

After editing your config, reload it with:

```bash
source ~/.zshrc
```

You can see that `ca` isn't a valid command, so the text is red.
But as soon as we finish typing `cat`, the text turns green!
And the autosuggestion means at any time we can just hit the Right Arrow key and complete the suggestion.

![ca command](/pics/syntax.png)

![cat command](/pics/syntax-1.png)

## Bat, Eza, and Zoxide

**Bat is a better `cat`.**  
Get syntax highlighting, line numbers, and Git integration.  
[Bat GitHub](https://github.com/sharkdp/bat)

```bash
brew install bat
```

cat 😬
![cat](/pics/cat.png)

bat 😎
![bat](/pics/bat.png)

**Eza is a better `ls`.**  
Replacement for `exa`, which is deprecated.  
Get colors, icons, tree views, Git status.  
[Eza GitHub](https://github.com/eza-community/eza)

```bash
brew install eza
```

![eza](/pics/eza.png)

Look at that — so much better than `ls`!

**Zoxide is a smarter `cd`.**  
Remembers directories you use frequently and lets you jump to them.  
[Zoxide GitHub](https://github.com/ajeetdsouza/zoxide)

```bash
brew install zoxide
```

![z desktop](/pics/z-desktop.gif)

**Add Aliases to .zshrc**

If you're used to your normal commands like me, just add some aliases to your `.zshrc` file:

```bash
# Aliases
alias cat="bat"
alias ls="eza -lao --git-repos --header --icons"
alias cd="z"
```

## Wrapping Up

I'll definitely keep tinkering with my setup, but for now I'm excited to be using some interesting new tools. 
Learning a bit about each one and reading why the creators built them is always fun — it's part of what keeps me constantly coming back for more when it comes to all things tech. 

Thanks for following along!