# Installation of edly tutor in your machine

## Edly tutor installation
You can install tutor as [Python package](https://docs.tutor.edly.io/install.html#python-package)

> [!NOTE]
> Before installing tutor through python, it is recommend to install it in a python virtual environment.
> Follow these steps to create a python virtual environment
> ```bash
> mkdir tutor-install
> ```
>
> Change into the ```tutor-install``` by using the command ```cd tutor-install```
>
> create a python virtual environment using the command below:
> ```bash
> python3 -m venv .venv
> ```
> You should install tutor inside the ```tutor-install``` directory

The commands to install tutor as python package are as follows:
```bash
pip install "tutor[full]"
```

You can check if tutor is installed in you machine using the following command:
```bash
tutor --version
```

You will see the version similar to this ```tutor, version 19.0.1```


After installing edly tutor, follow the docs to run [open-edx development](https://github.com/jayaramcloud/lidoku-docs/blob/main/openedx-setup/OPEN_EDX_DEVELOPMENT.md) locally