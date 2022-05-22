### install Git in Windows
For windows: https://git-scm.com/download/win
For Mac: Git is built-in

### Connect Git to VS Code
1) to generate access key:
    in terminal: ssh-keygen -t rsa -b 4096 -C "your_github_email@example.com"
2) Enter file in which to save the key: David_Geng_Key
3) Enter passphrase : (leave it blank)
4) Enter same passphrase : (leave it blank again)
5) type: ls | grep testkey
6) type: cat David_Geng_Key.pub
7) to copy the key to the clipboard: type: pbcopy < ~/David_Geng_Key.pub
8) paste the public key to github by opening setting in the homepage, then SSH and GPG keys
9) click on new SSH key, then paste the key there with a proper name. Save and close out the github
10) In terminal, start ssh-agent by type:
    $ eval "$(ssh-agent -s)"
    > Agent ID xxxxx

11) Modify ~/.ssh/config by copying following to the end of the file
    Host *
        AddKeysToAgent yes
        UseKeychain yes
        IdentityFile ~/.ssh/id_rsa (or PersonalKey)

12) Lastly, type
    $ ssh-add --apple-use-keychain ~/.ssh.id_rsa

Now, you can push to the github from vscode

