# Getting started

This section contains a guide for installing and configuring the project backend. The instruction will be accompanied by code layouts and comments to them.

## Ready, set, run !

### Getting a project

!!! info
	Be sure to have [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) installed

Download the project with the command:

``` bash
git clone https://github.com/alexfzero/be_kursach.git
```


### Installing dependencies

!!! info
	Be sure to have [python 3.10+](https://www.python.org/downloads/) installed


Go to the directory with the project and run the command to create a virtual environment

``` bash
python3 -m venv new_env
```

Activate virtual environment:

``` bash
source new_env/bin/activate
```

Check that you are on the same level as the "requirements" folder and run command:

``` bash
pip install -r requirements/local 
```

## Run

!!! note
	To access the guest OS from the main OS by accessing the IP address of the guest machine find in the "../be_kursach/config/settings.py" file the "ALLOWED_HOSTS" parameter and add the address of the guest machine there. Otherwise access will be granted by default on 127.0.0.1 and the port you specified

### To run from terminal

Go to the "../new_env/bin/activate" file and add the following lines to the end of the file:

!!! warning
	So that no one can decrypt the traffic in your application, generate your own secret key, for example, on the [djecrety.ir](https://djecrety.ir/) site for django and put the value instead of "YOUR_SECRET_KEY"

```py
export SECRET=YOUR_SECRET_KEY
export DEBUG=True
```

### To run from IDE

!!! info
	The examples use the PyCharm IDE

Go to the PyCharm environment settings. And change to like this

![PyCharm env settings](../assets/pycharm_env_settings.png)

Click on environment variables and add "SECRET" and "DEBUG" variables

![env var](../assets/env_var.png)

After that, you can start the project with the keyboard shortcut ++shift+f10++ or press the green start key in the upper right corner
