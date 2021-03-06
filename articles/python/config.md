# Configure Python

The Python engine exposes configuration options through the [boxfile.yml](http://docs.nanobox.io/boxfile/).

### Python Settings
The following setting allows you to define your Python runtime environment.

#### runtime
Specifies which Python runtime and version to use. The following runtimes are available:

- python-2.7
- python-3.4
- python-3.5
- python-3.6

```yaml
run.config:
  engine: python
  engine.config:
    runtime: python-3.5
```
