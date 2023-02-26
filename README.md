# mpgarate.com

```sh
# if needed
yay -S rvm

# At the time of writing github-pages does not support ruby 3
rvm install 2.7.5
rvm use 2.7.5
bundle update
bundle exec jekyll serve
```

For arch, sadly this is needed because GH pages uses an old ruby:
```sh
yay -S ruby2.7
bundle2.7 update
bundle2.7 install
bundle2.7 exec jekyll serve
```
