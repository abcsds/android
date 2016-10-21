# Termux Dotfiles

Requires instalation of [termux](https://termux.com/)

### SSH
Generate ssh key without passphrase (or else it will ask everytime you log in :P )
```
ssh-keygen -t rsa
```

Get the public key to your ssh folder (`~/.ssh`), and copy it to the authorized keys file (my key is called android.pub):
```
cat .ssh/android.pub >> .ssh/authorized_keys
```

You will have to root to change permissions:
```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
chmod 600 ~/.ssh/android.pub
```

You can now ssh with your private key:
```
ssh $IP -p 8022 -i ~/.ssh/android
```

Now to run the installer clone this repo:
```
apt update
apt install git
git clone https://github.com/abcsds/android .android
cd .android/script && bash bootstrap
```
