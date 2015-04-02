# Autologic Python

Manage Python installations from source. RedHat/RHEL based systems usually ship with Python 2.6 which is designed to work as a core OS component, not run user scripts/applications. This Role helps ease the management of a custom Python installation.

Defaults to Python 2.7.9, but this can be configured.

## Version

3.0.0

## Variables

```yaml
autologic_python_version: "2.7.9"
autologic_python_manage_deps: true 
autologic_python_manage_path: true
autologic_python_manage_pip: true
autologic_python_manage_virtualenv: true 
```

Here are some additional variables for fine tuning how ```setuptools``` is installed, as well as which version. These can be left alone unless the default version of ```14.3.1``` becomes critically out of date. We'll be keeping an eye on this, however.

```yaml
# Used to determine if virtualenv is already installed
autologic_python_virtualenv_creates: "/usr/local/bin/virtualenv"

# Used to determine if Pip is already installed
autologic_python_pip_creates: "/usr/local/bin/pip{{autologic_python_version[:3]}}"

# Used to install and precheck setuptools
autologic_python_setuptools_script: "https://bootstrap.pypa.io/ez_setup.py"
autologic_python_setuptools_version: "14.3.1" 
autologic_python_setuptools_creates: "/usr/local/lib/python{{autologic_python_version[:3]}}/site-packages/setuptools-{{autologic_python_setuptools_version}}-py{{autologic_python_version[:3]}}.egg"
```

## License

MIT.

## Author Information

- Michael Crilly
- Autologic Technology Ltd
- http://www.mcrilly.me/
