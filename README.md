# mpgarate.com

## Local setup on arch
Sadly this is needed because GH pages uses an old ruby.
(I also tried a dockerfile but hit dependency issues)
```sh
yay -S ruby2.7
bundle-2.7 update
bundle-2.7 install
bundle-2.7 exec jekyll serve
```

## Old notes

```sh
# install RVM
# https://rvm.io/

# At the time of writing github-pages does not support ruby 3
rvm install 2.7.5
rvm use 2.7.5
rvm exec bundle update
rvm exec bundle exec jekyll serve
```

