# ZenML Hub Plugin Template

This template repository can be used as a starting point to develop custom 
plugins for the ZenML Hub, which enables you to share your ZenML code with the
community and make it importable via `from zenml.hub.<plugin_name> import ...`.

## Plugin Development Process

### 1. Use this template to create a new public GitHub repository
To create your own plugin repository based on this template:
- [Open this template in GitHub](https://github.com/zenml-io/zenml-hub-plugin-template),
- Click on the big green **Use this template** button and choose **Create a new repository**,
- Enter a repository name, make sure to choose **Public** visibility, and click **Create repository from template**,

Next, clone your new plugin repository so you can make changes locally.

### 2. Copy code into `src/`
Copy the source code you want to share into the `src/` folder. Anything you put
here can later be imported from `zenml.hub.<your_plugin_name>`. E.g., if you
contribute a plugin `my_plugin` that defines a step `my_step` in `src/my_step.py` you can later import it via 
`from zenml.hub.my_plugin.my_step import my_step`.

If you have 
multiple files that import each other, make sure to use relative imports.

### 3. Update `requirements.txt`
If your plugin depends on any packages other than `zenml` itself, make sure to
include these in the `requirements.txt` file. Also, if your plugin only works
for certain versions of `zenml`, adjust the entry in `requirements.txt`
accordingly to indicate which versions are supported.

### 4. Update `README.md`
Lastly, delete this `README.md` file and replace it with your own README that
explains how your plugin can be used.

### 5. Submit your plugin to the ZenML Hub
After you have adjusted your plugin repository according to steps 2) to 4), push
your changes back to GitHub. Then, run `zenml hub push -i` in your terminal to 
start an interactive publishing process and provide the URL of your new plugin 
repository when prompted to do so.

## Folder Structure

Please make sure to preserve the overall folder structure that is suggested here:
```
├── README.md                       -- The README of the plugin -> TODO: explain your plugin here
│
├── requirements.txt                -- Package requirements of your plugin, needs to contain `zenml` -> TODO: update
│
├── src/                            -- Sources root -> TODO: put your code in here
```
