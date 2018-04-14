# .dotfiles

```shell
git init --bare $HOME/.dotfiles
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotfiles config --local status.showUntrackedFiles no

echo "alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'" >> $HOME/.zhrc
dotfiles remote add origin git@github.com:misho85/.dotfiles.git

dotfiles status
dotfiles add .zhrc
dotfiles commit -m "Add zhrc"
dotfiles add .bashrc
dotfiles commit -m "Add bashrc"
dotfiles push

git clone --separate-git-dir=$HOME/.dotfiles git@github.com:misho85/.dotfiles.git $HOME/dotfiles-tmp
cp -r ~/dotfiles-tmp/. ~
rm -rf dotfiles-tmp
```
