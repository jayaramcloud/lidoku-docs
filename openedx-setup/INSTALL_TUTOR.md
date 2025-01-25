# Installation of edly tutor and edly tutor main in your machine

## Edly tutor installation
You can install tutor from the [binary release](https://docs.tutor.edly.io/install.html#binary-release)

The commands to install tutor from the binary release are as follows:
```bash
sudo curl -L "https://github.com/overhangio/tutor/releases/download/v19.0.1/tutor-$(uname -s)_$(uname -m)" -o /usr/local/bin/tutor
```
```bash
sudo chmod 0755 /usr/local/bin/tutor
```

You can check if tutor is installed in you machine using the following command:
```bash
tutor --version
```

You will see the version similar to this ```tutor, version 19.0.1```

## Edly tutor main installation
You should also install tutor main from github, you can follow the [edly tutor main](https://docs.tutor.edly.io/tutorials/main.html#installing-tutor-main) installation here

The commands to install tutor main from the github are as follows:
```bash
git clone --branch=main https://github.com/overhangio/tutor.git
```
```bash
pip install -e "./tutor[full]"
```

You can check if tutor main is installed in you machine using the following command:
```bash
tutor --version
```

You will see the version similar to this ```tutor, version 19.0.1-main```

