# Create a Memcached Component

To add a Memcached to your app, add a data component to your boxfile.yml with the `image` set to `nanobox/memcached`.

```yaml
data.memcached:
  image: nanobox/memcached
```

**Note:** *For purposes of these guides, we'll use* `data.memcached` *as the component ID.* `memcached` *is a unique identifier that can be whatever you'd like. More information about component IDs is available in the [boxfile.yml documentation](https://docs.nanobox.io/boxfile/#component-ids).*


## Configure Memcached
The Memcached image exposes configuration options in the boxfile.yml. These options are nested under the `config` section of your data component. For all the available configuration options, view the [Memcached Config Options guide](configure.html).

```yaml
data.memcached:
  image: nanobox/memcached

  # optional memcached configs
  config:
    version: 1.4
```

## Build & Deploy
With your Memcached component included in your boxfile.yml, build a new runtime to apply the changes, then deploy your newly built runtime into your dev, sim, or production environment(s). In the deploy process, your Memcached component will be created.

```bash
# build a new runtime
nanobox build

# deploy to your dev platform
nanobox dev deploy
```