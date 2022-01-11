# Notes
These are my notes from building a sample toolbox; so that it can easily be installed with pip.

# Create package
- Fill out the `setup.cfg` and `setup.py` files
- Run `python setup.py sdist` to create the local files
- Alternatively simply push the project to Github and install it with `python -m pip install https://github.com/Antra/toolbox_project/tarball/master#egg=sample_toolbox`
  - and via requirements.txt file: `-e git+git://github.com/Antra/toolbox_project#egg=sample_toolbox`
- If the project is not in a separate repo, but part of e.g. `Playground` repo, then install it using the [subdirectory parameter](https://pip.pypa.io/en/latest/cli/pip_install/) with `python -m pip install -e "git+https://github.com/antra/playground.git#egg=sample_toolbox&subdirectory=toolbox_project"`
  - and via requirements.txt file: `-e "git+https://github.com/antra/playground.git#egg=sample_toolbox&subdirectory=toolbox_project"`