# Notes
These are my notes from building a sample toolbox; so that it can easily be installed with pip.

# Create package
- Fill out the `setup.cfg` and `setup.py` files
- Run `python setup.py sdist` to create the local files
- Alternatively simply push the project to Github and install it with `python -m pip install https://github.com/Antra/toolbox_project/tarball/master#egg=sample_toolbox`
  - and via requirements.txt file: `-e git+git://github.com/Antra/toolbox_project#egg=sample_toolbox`
- If the project is not in a separate repo, but part of e.g. `Playground` repo, then install it using the [subdirectory parameter](https://pip.pypa.io/en/latest/cli/pip_install/) with `python -m pip install -e "git+https://github.com/antra/playground.git#egg=sample_toolbox&subdirectory=toolbox_project"`
  - and via requirements.txt file: `-e "git+https://github.com/antra/playground.git#egg=sample_toolbox&subdirectory=toolbox_project"`


# Complex toolchain
I could even put each tool into its own `module` subfolder containing a setup.py and another subfolder named `module` containing the `module.py`.
But then I should remember to include a `readme.md` with each individual tool so I can remember how it works.

I.e.
- repository (`toolbox_project`)
    - toolchain (this folder)
        - module1
            - setup.py
            - module1
                - module1.py
                - readme.md
        - module2
            - setup.py
            - module2
                - module2.py
                - readme.md
        - module3
            - setup.py
            - module3
                - module3.py
                - readme.md


When the above structure is observed, the individual tools can be installed by (in this case `module1`):
```
pip install -e "git+https://github.com/Antra/toolbox_project.git#egg=module1&subdirectory=toolchain/module1"
```

Or have it in the requirements file (in this case `module1`):
```
-e "git+https://github.com/Antra/toolbox_project.git#egg=module1&subdirectory=toolchain/module1"
```
