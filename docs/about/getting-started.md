# Getting Started with MkDocs

An introductory tutorial!

------

## Requirements

MkDocs requires a recent version of [Python](https://www.python.org/) and the Python package manager, [pip](https://pip.readthedocs.io/en/stable/installing/), to be installed on your system.

You can check if you already have these installed from the command line:

```bash
$ python --version
Python 3.8.2
$ where python
C:\Program Files (x86)\Microsoft Visual Studio\Shared\Python37_64\python.exe
$ pip --version
pip 20.0.2 from /usr/local/lib/python3.8/site-packages/pip (python 3.8)
```

If you already have those packages installed, you may skip down to [Installing MkDocs](#installing-mkdocs).

If Python is installed but is not in your `PATH` environment variable then just add this path to it.

### Installing Python

Install [Python](https://www.python.org/) using your package manager of choice, or by downloading an installer appropriate for your system from [python.org](https://www.python.org/downloads/) and running it.

### Installing pip

If you're using a recent version of Python, the Python package manager, [pip](https://pip.readthedocs.io/en/stable/installing/), is most likely installed by default. However, you may need to upgrade pip to the lasted version:

```bash
pip install --upgrade pip
```

If you need to install pip for the first time, download [get-pip.py](https://bootstrap.pypa.io/get-pip.py). Then run the following command to install it:

```bash
python get-pip.py
```

## Installing MkDocs

Install the `mkdocs` package using pip:

```bash
pip install mkdocs
```

You should now have the `mkdocs` command installed on your system. Run `mkdocs --version` to check that everything worked okay.

```bash
$ mkdocs --version
mkdocs, version 1.2.0 from /usr/local/lib/python3.8/site-packages/mkdocs (Python 3.8)
```

!!! note

    If you are using Windows, some of the above commands may not work out-of-the-box.

    A quick solution may be to preface every Python command with `python -m` like this:

    ```bash
    python -m pip install mkdocs
    python -m mkdocs
    ```

    For a more permanent solution, you may need to edit your `PATH` environment variable to include the `Scripts` directory of your Python installation. Recent versions of Python include a script to do this for you. Navigate to your Python installation directory (for example `C:\Program Files (x86)\Microsoft Visual Studio\Shared\Python37_64\`), open the `Tools`, then `Scripts` folder, and run the `win_add2path.py` file by double clicking on it. Alternatively, you can download the [script](https://github.com/python/cpython/blob/master/Tools/scripts/win_add2path.py) and run it (`python win_add2path.py`).

## Installing Material theme for MkDocs

Material theme for MkDocs can be installed with `pip`:

```bash
pip install mkdocs-material
```

## Upgrading Material theme for MkDocs

Upgrade to the latest version with:

```bash
pip install --upgrade mkdocs-material
```

Show the currently installed version with:

```bash
pip show mkdocs-material
```

## Working with a project

Getting started is super easy.

To create a **new project**, run the following command from the command line:

```bash
mkdocs new my-project
cd my-project
```

Take a moment to review the initial project that has been created for you.

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

There's a single configuration file named `mkdocs.yml`, and a folder named `docs` that will contain your documentation source files (`docs` is the default value for the [docs_dir](https://www.mkdocs.org/user-guide/configuration/#docs_dir) configuration setting). Right now the `docs` folder just contains a single documentation page, named `index.md`.

MkDocs comes with a built-in dev-server that lets you preview your documentation as you work on it. Make sure you're in the same directory as the `mkdocs.yml` configuration file, and then start the server by running the `mkdocs serve` command:

```
$ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
[I 160402 15:50:43 server:271] Serving on http://127.0.0.1:8000
[I 160402 15:50:43 handlers:58] Start watching changes
[I 160402 15:50:43 handlers:60] Start detecting changes
```

Open up `http://127.0.0.1:8000/` in your browser, and you'll see the default home page being displayed.

## Building the site

That's looking good. You're ready to deploy the first pass of your `MkLorum` documentation. First build the documentation:

```bash
mkdocs build
```

This will create a new directory, named `site`. Take a look inside the directory:

```bash
$ ls site
about  fonts  index.html  license  search.html
css    img    js          mkdocs   sitemap.xml
```

Notice that your source documentation has been output as two HTML files named `index.html` and `about/index.html`. You also have various other media that's been copied into the `site` directory as part of the documentation theme. You even have a `sitemap.xml` file and `mkdocs/search_index.json`.

If you're using source code control such as `git` you probably don't want to check your documentation builds into the repository. Add a line containing `site/` to your `.gitignore` file.

```bash
echo "site/" >> .gitignore
```

If you're using another source code control tool you'll want to check its documentation on how to ignore specific directories.

## Other Commands and Options

There are various other commands and options available. For a complete list of commands, use the `--help` flag:

```bash
mkdocs --help
```

To view a list of options available on a given command, use the `--help` flag with that command. For example, to get a list of all options available for the `build` command run the following:

```bash
mkdocs build --help
```

## Deploying

The documentation site that you just built only uses static files so you'll be able to host it from pretty much anywhere. Simply upload the contents of the entire `site` directory to wherever you're hosting your website from and you're done. For specific instructions on a number of common hosts, see the [Deploying your Docs](https://www.mkdocs.org/user-guide/deploying-your-docs/) page.

## Getting help

See the [User Guide](https://www.mkdocs.org/user-guide/) for more complete documentation of all of MkDocs' features.

To get help with MkDocs, please use the [GitHub discussions](https://github.com/mkdocs/mkdocs/discussions) or [GitHub issues](https://github.com/mkdocs/mkdocs/issues).
