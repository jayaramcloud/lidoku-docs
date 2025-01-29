# Installation of edly tutor in your machine

## Edly tutor installation
You can install tutor as [Python package](https://docs.tutor.edly.io/install.html#python-package)

Create a directory named ```tutor-install``` by running the command ```mkdir tutor-install``` and navigate into the directory by running ```cd tutor-install```


### Creating a python virtual environment
Before installing tutor through python, it is recommend to install it in a python virtual environment.

Create a python virtual environment using the command below:
```bash
python3 -m venv .venv
```

Activate the virtual environment by running the command below
```bash
source ./.venv/bin/activate
```


### Installing tutor
The commands to install tutor as python package are as follows:
```bash
pip install "tutor[full]"
```


### Verifing the tutor installation
You can check if tutor is installed in your virtual environment using the following command:
```bash
tutor --version
```

You will see the version similar to this ```tutor, version 19.0.1```


### Adding tutor executable to the machine
Now we have installed tutor successfully, but the tutor command will work only inside the ```tutor-install``` directory.

To make the tutor run across the machine we want to create a symbolic link of the tutor executable from the virtual environment to the machine.

First get the path of the tutor executable by running the command inside the ```tutor-install``` directory.
```bash
which tutor
```

Now copy the output from the above command and paste in the below command
```bash
sudo ln -s <output_from_the_above_command> /usr/local/bin/
```

Now you can run tutor across the machine. You can verify this by running the following command
```bash
cd ~ && which tutor
```
It will output the path of the tutor executable similar to ```/usr/local/bin/tutor```


### Running open-edx development
After installing edly tutor, follow the docs to run [open-edx development](https://github.com/jayaramcloud/lidoku-docs/blob/main/openedx-setup/OPEN_EDX_DEVELOPMENT.md) locally
