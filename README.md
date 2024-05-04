# Tabby in zed

![image.png](https://s2.loli.net/2024/05/04/6fx1A9ZpYkOjnV3.png)

First install Tabby and start server

```bash
brew install tabbyml/tabby/tabby

# My machine is M1 Pro, I running StarCoder-3B
# If the machine is poor, try using 1B?
# TODO: custom export port and host?
tabby serve --device metal --model StarCoder-3B
```

And edit config(`tabby-agent`): $HOME/.tabby-client/agent/config.toml

```toml
# https://tabby.tabbyml.com/docs/extensions/configurations
[server]
# I don't know why http://localhost:8080 doesn't work
# `curl http://localhost:8080/v1/health` in zed extension not work?
endpoint = "http://0.0.0.0:8080"

[logs]
level = "silent" #  "debug"

[anonymousUsageTracking]
disable = true # I don't want to be tracked
```

# TODO

It seems that the suggestion did not take effect? this is VScode

![image.png](https://s2.loli.net/2024/05/04/Dd6prAnj5igHWez.png)