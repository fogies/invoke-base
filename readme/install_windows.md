# Dependency Installation for Windows

## Installing Python

[https://www.python.org/ftp/python/3.6.6/python-3.6.6.exe](https://www.python.org/ftp/python/3.6.6/python-3.6.6.exe)

This documentation assumes an installation path of `c:\Python36`.

When installing Python:

- Choose 'Customize Installation'
- On 'Optional Features':

  Check 'pip'.

  Uncheck 'Documentation', 'tcl/tk and IDLE', 'Python test suite', 'py launcher', and 'for all users (requires elevation)'.

- On 'Advanced Options':

  Check 'Install for all users' and 'Precompile standard library'.

  Uncheck 'Create shortcuts for installed applications', 'Add Python to environment variables', 'Download debugging symbols', and 'Download debug binaries (requires VS 2015 or later)'.

  Set an installation path of `c:\Python36`.

  Uncheck all options.

- On 'Setup was successful':

  If present, choose 'Disable path length limit'.

### Creating a Virtual Environment and Installing Dependencies

Create the virtual environment. From the working directory of our project (e.g., `c:\devel\invoke-base`):

~~~
c:\Python36/python.exe -m venv env36
~~~

This will create a directory for the virtual environment (e.g., `c:\devel\invoke-base/env36/`).

Next activate that virtual environment and install our Python dependencies:

~~~
env36/Scripts/activate.bat
pip install -r requirements3.txt
~~~

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