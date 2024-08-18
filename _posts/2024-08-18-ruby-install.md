---
layout: post
categories: tips
title: "Updating Ruby in arm64 M2 Mac"
---

I made this blog today and added Gemfile, then found out that I have ruby version 2.6, while bundle needed ruby version over 3. So I tried `rbenv install 3.3.4` with no success. Interestingly, with M2 chip, `rbenv install X.X.0` works fine. So I installed 3.3.0. I wonder why. There was an [open issue in github](https://github.com/rbenv/ruby-build/discussions/1961) but yeah I was too lazy to read it...

I successfully installed 3.3.0 and checked `ruby -v` and the version was not updated. wtf

Then I found out [this article](https://dev.to/luizgadao/easy-way-to-change-ruby-version-in-mac-m1-m2-and-m3-16hl) and followed step 7.

1. Open `~/.zprofile`...whatever that is... with vim
2. add these lines :
```bash
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init - zsh)"
```
3. `esc` and `:wq`
4. `source ~/.zprofile` to apply change
5. `ruby -v` to check if it was successfully updated

and I installed bundler with `gem install bundler` (obviously)
