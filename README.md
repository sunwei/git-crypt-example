# Example for git-crypt 

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## Usage

Take DNSPod provider for example, and issue your domain in all easy way:

1. Setup git-crypt, init and add gpg user, run `setup.sh`
```
./setup.sh
```
2. Add git attributes file to the folder that you want to encrypt
```
touch .gitattributes
set +o histexpand
printf -- "*.env filter=git-crypt diff=git-crypt\n.gitattributes !filter !diff\n" > .gitattributes
```
3. Add `test.env`, and we can change the pattern in git attributes file `*.env`
```
touch test.env
echo "anthing you like here" > test.env
```
4. Check file status, and you will find `test.env` encrypted
```
git-crypt status
```

## License
This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details
