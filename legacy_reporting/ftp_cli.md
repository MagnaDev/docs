# FTP CLI

## Instructions

Open a command prompt. This can be done by pressing a combination of the
**Win** + **R** keys. Type `cmd` in the Run window that appears and press 
**Ok**.

In the command prompt, type `ftp smc1`.

When prompted, enter your username and password.

!> If you enter your password incorrectly, you will still be passed to the FTP
    CLI. You will still need to log in and this can be attempted again by 
    typing `user <username>`.

Once logged in, you can issue the following command to extract a dataset to your 
computer.

```
get '<username>.<qualifier>.unload' <filepath>

# as an example
get 'sv0849.tcon000.unload' C:/Downloads/GRSTrack/grt_host.txt
```

When finished, type `quit` to leave the FTP CLI and then `exit` to close the
command prompt.