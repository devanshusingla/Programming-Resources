## How to enable executing .bashrc for subfolders also.

Just add following line in ~/.bashrc

```
PROMPT_COMMAND='if [[ "$bashrc" != "$PWD" && "$PWD" != "$HOME" && -e .bashrc ]]; then bashrc="$PWD"; . .bashrc; fi'
```

And whenever you will visit your folder .bashrc in that folder will be executed.

##### source

[folder specific .bashrc](https://superuser.com/questions/915703/is-there-a-folder-specific-bashrc-or-bash-profile)
