# Running open-edx development using edly tutor in your machine

## Installing open-edx latest release
Clone the official [edx-platform](https://github.com/openedx/edx-platform) latest release ```open-release/sumac.master``` as of now:
```bash
git clone -b 'open-release/sumac.master' https://github.com/openedx/edx-platform.git
```

## Running open-edx development locally
After installing tutor, you can run [open-edx development](https://docs.tutor.edly.io/dev.html) using tutor.

Before running open-edx, make sure you have the following hosts in ```/etc/hosts```
```
127.0.0.1 local.openedx.io studio.local.openedx.io meilisearch.local.openedx.io apps.local.openedx.io
```

Mount the open-edx repo that you have cloned by run the following command:
```bash
tutor mounts add ./edx-platform
```

Run the following command to dockerize the open-edx repo
```bash
tutor images build openedx-dev
```

Run the following command to install the docker images for open-edx and running open-edx in development
```bash
tutor dev launch
```

Your platform name/title [My Open edX] lidoku
Your public contact email address [contact@local.openedx.io] jayaram.linux@gmail.com
The default language code for the platform [en] 



Run the command to add the necessary configuration to tutor
```bash
tutor config save --set ENABLE_WEB_PROXY=true
```

Once you run the command ```tutor dev launch```, it will automatically install the docker images and run the dev server automatically.

At any point of time, you can run the following command to stop the dev server. This will stop all the docker containers as well
```bash
tutor dev stop
```

You can start the dev server by running the following command. This will start the dev containers as well
```bash
tutor dev start
```

> [!WARNING]
> You have to stop the dev containers to create an admin user or to create a demo course

Create an admin user
```bash
tutor local do createuser --staff --superuser <username> <email>
```

Create a demo course
```bash
tutor local do importdemocourse
```

Once setup is complete, the platform will be running in the background:
- LMS will be accessible at [http://local.openedx.io:8000](http://local.openedx.io:8000)
- CMS will be accessible at [http://studio.local.openedx.io:8001](http://studio.local.openedx.io:8001)

