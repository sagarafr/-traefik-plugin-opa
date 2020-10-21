# README

A Traefik middleware that support OPA (Open Policy Agent) for Authorization management : [Issue #4894](https://github.com/traefik/traefik/issues/4894)

## Configuration

### Normal Usage

Static configuration:
```yaml
pilot:
  token: xxx

experimental:
  plugins:
    moduleName: github.com/sagarafr/traefik-plugin-opa
    version: X
```

Dynamic configuration:
```yaml
http:
  middlewares:
    my-opa-plugin:
      plugin:
        opa:
          path: /some/path/to/opa/policy/dir
```

### Dev Usage

Static configuration:
```yaml
pilot:
  token: xxx

experimental:
  devPlugin:
    moduleName: github.com/sagarafr/traefik-plugin-opa
    goPath: /some/path/to/opa/plugins/go
```

Dynamic configuration:
```yaml
http:
  middlewares:
    my-opa-plugin:
      plugin:
        dev:
          path: /some/path/to/opa/policy/dir
```
