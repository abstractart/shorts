# rbenv
## Install on Ubuntu
```sh
#!/bin/bash

sudo apt install -y build-essential
sudo apt install -y libssl-dev libreadline-dev zlib1g-dev
wget -q https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer -O- | bash
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
echo "eval '$(rbenv init -)'" >> ~/.zshrc
wget -q https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor -O- | bash
rbenv install 2.5.3
```
