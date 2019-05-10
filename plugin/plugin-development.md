---
description: Setup environment for plugin development.
---

# Plugin Development

## Create a Plugin Project

## Set Test Project Root for the Plugin to Manage

## Test Plugin in Development Mode

## Test Plugin in Production Mode

## Test Plugin in Command Line Mode

Within a terminal, go to the  the project root the plugin is loaded with, you can use `rekit` command line interface to manage project elements like add/move/remove. To let `rekit` know your plugin, you need to set `REKIT_PLUGIN_DIR` environment variable before running the `rekit` command. Say that your plugin manages a new element type of `page` , you can test it with below command:

```bash
> export REKIT_PLUGIN_DIR=/my/workspace/plugin-project-root
> rekit add page my-page
```

If not set the environment variable, Rekit will not load your plugin and you will see errors like below:

![](../.gitbook/assets/image%20%281%29.png)

## Deploy Plugin to Local Registry

To use the plugin locally in other Rekit Studio instance, you need to deploy built bundle into local Rekit plugin registry. It's very simple, just run npm script `npm run deploy` , or you can run it with Rekit Studio's scripts manager:

![Deploy Plugin Using Rekit Studio](../.gitbook/assets/image%20%282%29.png)

To undeploy the plugin, just run the command `npm run undeploy` .

## Publish Plugin

To distribute you plugin, you need to publish to npm registry \(either public or private\).

