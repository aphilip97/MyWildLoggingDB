# 2019/07/22 - 11:19 - First Party Authentication - Completed

So the server had no problems with it. Neither did Auth0. The problem was that the `launch.json` was not configured properly. The `RSA_URI` environment variable for both the local development server's `launch.json` and the deployed server's *Config Vars* was _**WRONG**_. It had an extra `/` in it.

Fixing it made it all work. :)
