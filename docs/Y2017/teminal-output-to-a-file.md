title: Save terminal output to a file
date: 2017

All output will be sent to terminal
and file.

```sh
bash-4.2$ command |& tee output.txt
```

Append to existing file

```sh
bash-4.2$ command |& tee -a output.txt
```

[Source: Stackoverflow](https://askubuntu.com/a/731237)
