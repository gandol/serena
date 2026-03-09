# The Dashboard and GUI Tool

Serena comes with built-in tools for monitoring and managing the current session:

* the **web-based dashboard** (enabled by default)
  
  The dashboard provides detailed information on your Serena session, the current configuration and provides access to logs.
  Some settings (e.g. the current set of active programming languages) can also be directly modified through the dashboard.

  The dashboard is supported on all platforms.
  
  By default, it will be accessible at `http://localhost:24282/dashboard/index.html`,
  but a higher port may be used if the default port is unavailable/multiple instances are running.

  **We recommend always enabling the dashboard**. The dashboard runs in the background; a browser window
  is not opened automatically (you can enable this if desired, see below).

* the **GUI tool** (disabled by default)
  
  The GUI tool is a native application window which displays logs.
  It furthermore allows you to shut down the agent and to access the dashboard's URL (if it is running). 

  This is mainly supported on Windows, but it may also work on Linux; macOS is unsupported.

Both can be configured in Serena's [configuration](050_configuration) file (`serena_config.yml`).
The GUI tool, if enabled, will automatically be opened as soon as the Serena agent/MCP server is started.
For the dashboard, the background server always starts when `web_dashboard` is enabled, but the browser
is not opened automatically by default (see below for how to enable this).

## Enabling Automatic Browser Opening

The dashboard runs in the background whenever Serena starts, but it does **not** open a browser window
automatically by default. You can enable automatic browser opening by setting
`web_dashboard_open_on_launch: True` in your `serena_config.yml` or by passing `--open-web-dashboard True`
to the `start-mcp-server` CLI command.

When automatic opening is disabled (the default), you can access the dashboard by:
* asking the LLM to "open the Serena dashboard", which will open the dashboard in your default browser
  (the tool `open_dashboard` is enabled for this purpose, provided that the dashboard is active, 
  not opened by default and the GUI tool, which can provide the URL, is not enabled)
* navigating directly to the URL (see above)
