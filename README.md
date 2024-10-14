# Openfire Launcher action

An action for launching [Openfire](https://github.com/igniterealtime/Openfire), an XMPP server implementation, in the context of a Github Action workflow. It's not intended for anything production-facing, or even really user-facing. It's useful for CI-based short-lived actions that need an XMPP server.

## Inputs

### version

Version of Openfire to launch, in the form `a.b.c`, as seen in [Openfire Releases](https://github.com/igniterealtime/Openfire/releases).

example:

```yaml
      - name: Run Openfire
        uses: igniterealtime/openfire-launcher
        with:
          version: 4.9.0
```

### daily

Ignores any provided version, and loads the latest daily build of Openfire instead.

example:

```yaml
      - name: Run Openfire
        uses: igniterealtime/openfire-launcher
        with:
          daily: 'true'
```

### config

By default, the action launches with the demoboot config (the config file is [here](https://github.com/igniterealtime/Openfire/blob/main/distribution/src/conf/openfire-demoboot.xml), some docs [here](https://download.igniterealtime.org/openfire/docs/latest/documentation/client-minimal-working-example-smack.html#preparations)).

You can pass a different config file in to get alternative or additional config (e.g. adding additional configuration for plugins).

example:

```yaml
      - name: Run Openfire
        uses: igniterealtime/openfire-launcher
        with:
          config: ./my-config.xml
```
