title: uwsgi Master Process
date: 2013

 If you are just getting your feet wet with uWSGI, you might have run into the following error when running it.

`*** WARNING: you are running uWSGI without its master process manager ***`

To run uWSGI with the master process add the flag ```-M``` flag when running uWSGI. Then you will get the following nice message.

`spawned uWSGI master process (pid: 755)`

The Master process manager will respawn your process if or when it dies. See this [reference doc](https://uwsgi-docs.readthedocs.org/en/latest/Options.html?highlight=options#master) about the flag.
