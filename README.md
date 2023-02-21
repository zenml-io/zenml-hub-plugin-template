# ZenML Hub Plugin Template

This template repository can be used as a starting point to develop custom 
plugins for the ZenML Hub.

## Plugin Development Process

### 1. Use this template to create a new public GitHub repository
To create your own plugin repository based on this template:
- [Open this template in GitHub](https://github.com/zenml-io/zenml-hub-plugin-template),
- Click on the big green **Use this template** button and choose **Create a new repository**,
- Enter a repository name, make sure to choose **Public** visibility, and click **Create repository from template**,

Next, clone your new plugin repository so you can make changes locally.

### 2. Copy your source code into `src/zenml/hub/`
The relative path within this repository will determine how your plugin can
later be imported. E.g., if you want to contribute a step `my_step` and put it
under `src/zenml/hub/my_plugin/my_step.py` you can later import it via 
`from zenml.hub.my_plugin.my_step import my_step`.

**Warning:** Make sure to not add any `__init__.py` directly into 
`src/zenml/hub`. Also, do not put anything into `src/` or `src/zenml` directly. 
Otherwise the Hub will deny your request when submitting your plugin later.
Also, make sure to delete the `my_plugin` example folder after you have added
your own code.

### 3. Update `requirements.txt`
If your plugin depends on any packages other than `zenml` itself, make sure to
include these in the `requirements.txt` file. Also, if your plugin only works
for certain versions of `zenml`, adjust the entry in `requirements.txt`
accordingly to indicate which versions are supported.

### 4. Update `README.md`
Lastly, delete this `README.md` file and replace it with your own README that
explains how your plugin can be used. The first line of the README will be
displayed as plugin description on the overview page in the hub.

### 5. Submit your plugin to the ZenML Hub
After you have adjusted your plugin repository according to steps 2) to 4), push
your changes back to GitHub. Then, run `zenml hub push -i` in your terminal to 
start an interactive publishing process during which you will be prompted to
provide the URL of your new plugin repository.

## Folder Structure

Please make sure to preserve the overall folder structure that is suggested here:
```
├── LICENSE                         <- The Apache License under which the plugin will be published -> do not modify!
│
├── README.md                       <- The README of the plugin -> TODO: explain your plugin here
│
├── requirements.txt                <- Package requirements of your plugin, needs to contain `zenml` -> TODO: update
│
├── src/                            <- Sources root, may only contain `zenml`
│   ├── zenml/                      <- `zenml` subdir, may only contain `hub`
│   │   ├── hub/                    <- `zenml.hub` module -> TODO: put your code in here
│   │   │   ├── my_plugin/          <- `zenml.hub.my_plugin` example module -> TODO: delete
```
