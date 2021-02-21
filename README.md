# Install-Python-Libraries-on-Macbook-m1
This repository will collect general installation methods for python libraries on MacBook with Apple silicon.


<h2>1. Install Matplotlib</h2>
<b>1.1 Install Homebrew</b>

Type in your terminal (not in rosetta environment):

` /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`


Then add homebrew's path to the variable path:

`echo 'eval $(/opt/homebrew/bin/brew shellenv)' >> /Users/bcghostpc/.zprofile
    eval $(/opt/homebrew/bin/brew shellenv)`
    
<b>1.2 Install libjpeg</b>

`brew install libjpeg`

<b>1.3 Install Matplotlib</b>

In the virtual environment, type:

`pip install matplotlib`


<h2>2. Install tensorflow </h2>

Type in terminal:

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/apple/tensorflow_macos/master/scripts/download_and_install.sh)"`

then name your virsual environment's folder

<h2>3. Install pandas</h2>

In your virtual environment, type:

`pip install cython`

`git clone https://github.com/pandas-dev/pandas.git`

`cd pandas`

`python3 setup.py install`

<h2>4. Install jupyter notebook</h2>
In your virtual environment, type:

`pip install notebook`

Then go to `lib/python3.8/site-packages/ipykernel`

Edit the `eventloops.py` file using `nano eventloops.py`

In the _use_appnope() function, edit the return line as follows:

`return sys.platform == 'darwin' and V(platform.mac_ver()[0]) >= V('10.9') and platform.mac_ver()[2] != 'arm64'`

<h2> Appendix </h2>

<b> About Virtual Environment </b>

You can create a virtual environment by:

`python3 -m venv <name>`

After creating the environment, you can activate the environment by:

`source <name>/bin/activate`

To exit the environment, type:

`deactivate`

# Reference

https://brew.sh/

https://github.com/apple/tensorflow_macos

https://stackoverflow.com/questions/65084318/trouble-installing-pandas-on-new-macbook-air-m1

https://alexslobodnik.medium.com/apple-m1-matplotlib-python-and-jupyter-lab-551646b9a8cd

https://towardsdatascience.com/how-to-run-jupyter-notebooks-on-an-apple-m1-mac-ac3a8bf39c6c
