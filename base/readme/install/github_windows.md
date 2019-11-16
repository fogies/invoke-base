## Installing GitHub Desktop

Documentation assumes use of GitHub Desktop:

<https://desktop.github.com/>

Documentation assumes GitHub Desktop uses a `Command Prompt` shell, configured via:

```
File > Options... > Advanced > Shell
```

For seamless authentication via SSH private key from the shell:

- Ensure you have an SSH key associated with your account:

    ```
    <https://github.com/settings/keys>
    ```

- Place the private key in your SSH directory (e.g., at `C:\Users\jfogarty\.ssh\github_rsa`)

- Ensure an SSH configuration file (e.g., at `C:\Users\jfogarty\.ssh\config`).

  Specify use of private key as an identity file:

    ```
    Host github.com
    User git
    IdentityFile /C/Users/jfogarty/.ssh/github_rsa
    ```

- Modify your Git configuration (e.g., at `C:\Users\jfogarty\.gitconfig`).

  Specify use of that SSH identity instead of HTTPS:

    ```
    [url "git@github.com:"]
	    insteadOf = https://github.com/
	```
