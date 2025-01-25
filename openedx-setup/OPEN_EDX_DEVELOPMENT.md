# Running open-edx development using edly tutor in your machine

## Running open-edx development locally
After installing tutor, you can run open-edx development using tutor.

Clone the official [edx-platform](https://github.com/openedx/edx-platform) repository by the following command:
```bash
git clone https://github.com/openedx/edx-platform.git
```

After cloning the open-edx repo, run the following command:
```bash
tutor mounts add ./edx-platform
```

Run the following command to install the required images for open-edx
```bash
tutor images build openedx-dev
```

Before running open-edx, make sure you have the following hosts in ```/etc/hosts```
```
127.0.0.1 local.openedx.io studio.local.openedx.io meilisearch.local.openedx.io apps.local.openedx.io
```

Run the following command to run open-edx development
```bash
tutor dev launch
```

Once setup is complete, the platform will be running in the background:
LMS will be accessible at [http://local.openedx.io:8000](http://local.openedx.io:8000)
CMS will be accessible at [http://studio.local.openedx.io:8001](http://studio.local.openedx.io:8001)

Optionally, You can test the open-edx development working perfectly by removing ```meilisearch.local.openedx.io``` from ```127.0.0.1 local.openedx.io studio.local.openedx.io meilisearch.local.openedx.io apps.local.openedx.io``` in ```/etc/hosts```
