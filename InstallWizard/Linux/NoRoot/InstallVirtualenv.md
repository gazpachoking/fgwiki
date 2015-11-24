# Install virtualenv

### Download

Download the virtualenv `tarball` from:

http://pypi.python.org/pypi/virtualenv

Extract it:


    tar xvfz virtualenv-tip.gz


You can't install the package with the included `setup.py`, but you can still use the `virtualenv.py` in it.

### Create the environment


    python virtualenv.py ~/flexget/
**Note:** if you plan to use the [[deluge|Plugins/deluge]] plugin, you need to build your virtualenv with the --system-site-packages option: `python virtualenv.py --system-site-packages ~/flexget/`

Now you have created isolated python environment (virtualenv).

## Continue

[[Install [[FlexGet]]|InstallWizard/Linux/NoRoot/InstallVirtualenv/FlexGet]]
